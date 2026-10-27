# TagScanner

[開啟網站](https://robin840211.github.io/tagscanner/) · [原始碼](https://github.com/robin840211/AnyTagScanner)

使用相機或圖片辨識 QR Code、常見條碼、ArUco 與 AprilTag。

## 發布

此 repository 管理網站發布流程，應用程式位於 `AnyTagScanner`。

1. 將應用程式更新推送到 `AnyTagScanner/main`。
2. 本 repo 每小時第 17、47 分鐘檢查來源版本；有新版本時，執行檢查、測試、靜態建置與發布。
3. 如需立即更新，開啟 [Actions → Publish TagScanner](https://github.com/robin840211/tagscanner/actions/workflows/publish.yml)，按 **Run workflow**，選擇 `main`。
4. `resolve`、`build`、`deploy` 成功後，開啟網站。版本相同的定時檢查會略過 `build` 與 `deploy`。

發布記錄位於 [build.json](https://robin840211.github.io/tagscanner/build.json)，包含原始碼 commit、發布設定 commit 與 Actions 執行連結。

GitHub 排程可能延遲。公開 repo 連續 60 天沒有活動時，GitHub 會停用排程；可在 Actions 頁面重新啟用。手動發布適合需要立即更新的情況。

## 設定

- **Settings → Pages → Source**：`GitHub Actions`。
- 工作流程以唯讀權限讀取公開的 `AnyTagScanner`，部署 job 使用 Pages 與 OIDC 權限。
- 正式路徑：`/tagscanner`；建置環境使用 Node.js 24。
- 建置失敗時，Actions 會顯示失敗步驟；修正原始碼後再次執行發布。
- 回復版本時，在 `AnyTagScanner/main` 提交 revert，再執行發布。
