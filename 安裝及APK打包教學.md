# Stepwgn 入油管家 v1.0.3 — 手機 APK、電腦安裝及跨裝置同步教學

本套件包含完整的網頁程式、電腦桌面安裝檔 (PWA) 及雲端編譯 Android APK 設定，全程毋須在電腦安裝 Android Studio。

---

## 一、Windows / Mac 電腦下載安裝（變成獨立桌面程式）

### 方法 A：直接開啟（最快捷，零設定）
1. 解壓本 ZIP 檔，打開 `www` 資料夾。
2. 雙擊 `index.html` 即可用 Chrome / Edge 使用，所有資料自動儲存在本機瀏覽器。

### 方法 B：透過 GitHub Pages 安裝成獨立 Windows 桌面 App（推薦）
1. 在 GitHub 建立一個新的 Repository（例如 `stepwgn-fuel-tracker`），將本 ZIP 解壓後的全部檔案（包含 `.github` 資料夾）上傳上去。
2. 進入 Repository 的 **Settings → Pages**，選擇從 `main` 分支部署（或將 `www` 內檔案放到根目錄 / `docs`）。
3. 用 Chrome 或 Edge 開啟你的 GitHub Pages 網址，點擊網址列右邊的 **「安裝應用程式」** 圖示，就會在 Windows 桌面及開始功能表建立「Stepwgn 入油管家」獨立程式圖示。

---

## 二、手機變身 Android APK 檔（GitHub Actions 雲端自動編譯）

1. 將本 ZIP 解壓後的全部檔案推送（上傳）到你的 GitHub Repository。
2. 在 GitHub 頁面上方點擊 **Actions** 分頁，你會見到 `Build Stepwgn Fuel Tracker APK` 自動開始執行（約需 3–5 分鐘）。
3. 編譯完成（出現綠色勾號）後，點擊該次執行紀錄，拉到最底 **Artifacts** 下載 `Stepwgn-Fuel-Tracker-v1.0.3-APK`。
4. 解壓下載的檔案取得 `.apk`，傳送到你的 Samsung / Android 手機直接點擊安裝即可！
   - *提示*：每次更新檔案推送到 GitHub，`versionCode` 會自動遞增。如日後要啟用正式 Release 固定簽名覆蓋升級，只需在 GitHub Secrets 加入你的固定 Keystore 即可。

---

## 三、手機 APK ↔ 電腦 雲端雙向同步設定（GitHub Gist）

1. 登入 GitHub，右上角頭像 → **Settings** → 最底 **Developer settings** → **Personal access tokens** → **Tokens (classic)** → **Generate new token (classic)**。
2. Note 填 `Stepwgn Sync`，權限**只需勾選 `gist`**，按最底產生並複製 `ghp_...` 字串。
3. 在手機（或電腦）打開 **Stepwgn 入油管家 →「同步與安裝」分頁**：
   - 貼上剛才的 Token（Gist ID 首次可留空）。
   - 按 **「智能雙向合併同步」**，系統會自動建立一個私人雲端 Gist 並顯示一組 **Gist ID**。
4. 複製該組 **Gist ID** 及同一組 Token，貼到另一部裝置（電腦或手機）的「同步與安裝」分頁並儲存。
5. 以後無論在手機入油還是電腦批量匯入 Excel，只要按右上角 **「同步」** 按鈕，兩邊紀錄就會自動合併同步！
