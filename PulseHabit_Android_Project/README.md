# PulseHabit Android APK 打包工程说明

由于云端沙箱环境未内置 10GB+ 的 Android SDK 二进制编译链，本压缩包已为你配置好完整的 **Android 原生 WebView 容器工程**（已开启 `DOMStorage` 本地持久化，内置移动端触控自适应版 `index.html`）以及 **GitHub Actions 免环境自动打包脚本**。

---

## 方法一：免打包，直接在手机桌面生成全屏 App 图标（最快，耗时 10 秒）
1. 将单独提供的 `habit_tracker_mobile.html` 发送到手机（微信/Telegram/云盘均可）。
2. 用手机浏览器（Android 推荐 **Chrome / Edge**，iOS 推荐 **Safari**）打开该文件。
3. 点击浏览器菜单中的 **「添加到主屏幕」(Add to Home Screen)**，即可像原生 App 一样从手机桌面全屏启动，打卡数据永久保存在手机本地。

---

## 方法二：使用手机端一键转 APK 工具（耗时 30 秒，无需电脑配置）
1. 在电脑端使用免费工具 **Website 2 APK Builder**（或手机端应用 **HTML2APK / WebIntoApp**）。
2. 选择 `Local HTML Website`，导入 `app/src/main/assets/index.html`（即移动版单文件），点击 **Generate APK** 即可在数秒内输出 `.apk` 安装包。

---

## 方法三：GitHub Actions 云端自动编译 APK（零本地环境配置）
1. 将本压缩包解压后上传到你的任意 GitHub 仓库（公开或私有均可）。
2. 打开仓库顶部的 **Actions** 标签页，运行 `Build PulseHabit Android APK` 工作流。
3. 约 1~2 分钟后，在页面底部的 **Artifacts** 区域即可直接下载编译好的 `PulseHabit-debug-apk.zip`（内含 `app-debug.apk`）。

---

## 方法四：本地 Android Studio / Gradle 一键编译
如果你电脑上装有 Android Studio 或 Android SDK：
```bash
gradle assembleDebug
```
编译生成的 APK 位于：`app/build/outputs/apk/debug/app-debug.apk`。
