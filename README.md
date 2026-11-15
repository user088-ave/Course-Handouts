# Course-Handouts：《人工智慧概論》學習講義

課程講義內容統整。這是一個個人學習用的靜態網站，把每週《人工智慧概論》的上課投影片整理成好讀的筆記，方便課後複習與重點統整。

**線上瀏覽：** https://user088-ave.github.io/Course-Handouts/

## 特色

- **紙本講義風格**：米白背景、襯線標題、琥珀色重點提示框，閱讀起來像翻筆記本。
- **每個單元結構一致**：導覽列、標頭、學習目標、核心內容、上一／下一單元按鈕。
- **附生活化比喻**：抽象的 AI 概念盡量搭配淺顯的例子，方便理解與記憶。
- **純靜態、零建置**：只有 HTML、CSS 與 Tailwind CDN，不需要 npm 或資料庫，直接用 GitHub Pages 託管。
- **可由 AI 接手維護**：專案規則寫在 [`AGENTS.md`](./AGENTS.md)，新增內容時 AI 能照同一套規範完成。

## 單元目錄

| 單元 | 主題 | 內容重點 |
| --- | --- | --- |
| 01 | [緒論與什麼是 AI](./lessons/01-introduction.html) | AI 三起兩落、關鍵里程碑、應用領域與未來趨勢、AI 的四種定義、圖靈測試、理性代理人 |
| 02 | [搜尋演算法](./lessons/02-search-algorithms.html) | BFS／DFS、爬山法、最佳優先搜尋、分支界限法（含旅行推銷員問題）、A* 演算法、作業 1（數獨） |

編號可以不連續，跳號代表該週沒有講義。

## 專案結構

```text
Course-Handouts/
├── AGENTS.md                      # AI 專屬開發與維護規則
├── README.md                      # 專案說明（本檔案）
├── index.html                     # 課程總覽與單元目錄首頁
├── assets/
│   └── style.css                  # 自訂字體與紙張風微調樣式
└── lessons/                       # 所有單元講義
    ├── 01-introduction.html
    └── 02-search-algorithms.html
```

## 技術與設計規範

- HTML5 + [Tailwind CSS](https://tailwindcss.com/)（CDN）+ 原生 JavaScript
- 標題使用襯線字體，內文行高寬鬆，重點使用 `bg-amber-50 border-amber-300` 提示框
- 內容使用繁體中文（台灣慣用術語）
- 完整規則請見 [`AGENTS.md`](./AGENTS.md)

## 本機預覽

不需要安裝任何套件。可以直接用瀏覽器開啟 `index.html`，或在專案根目錄啟動簡易伺服器：

```bash
python3 -m http.server 8000
```

然後開啟 http://localhost:8000。

## 新增一個單元

1. 在 `lessons/` 新增檔案，命名為 `XX-topic-slug.html`（兩位數編號 + 全小寫英文短標題，用連字號分隔），例如 `03-knowledge-representation.html`。
2. 依標準結構撰寫頁面：頂部導覽列、講義標頭、學習目標、核心內容、底部導覽列。`lessons/` 內的連結一律使用 `../` 指回上一層。
3. **同步更新 `index.html`**，把新單元加進目錄清單。
4. 把前一單元底部「下一單元」按鈕改成連結，並讓新單元的「上一單元」指回去。
5. Commit 並 push 到 `main`，GitHub Pages 會自動更新。

### 請 AI 協助新增

把新單元的投影片或 PDF 交給 AI，並請它先閱讀 `AGENTS.md`，再依規則建立新頁面、更新首頁與前後單元的導覽連結。例如：

> 請先讀 `AGENTS.md`，再依規範把這份 PDF 整理成 `lessons/03-xxx.html`，並同步更新 `index.html`。

## 部署

網站由 GitHub Pages 託管：到 **Settings → Pages**，Source 選擇部署分支（`main`）的根目錄即可。因為是純靜態檔案，不需要任何建置步驟。

## 注意事項

- 本專案為個人學習筆記，內容整理自《人工智慧導論》課程投影片（授課教師：周信宏），僅供個人複習使用。
- 筆記中若發現與投影片不一致之處，會在頁面中以提示框標註，方便日後向老師確認。
- 部分比喻與驗算為整理時自行補充，不一定出自原投影片，請以課堂內容為準。
