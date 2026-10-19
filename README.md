# carpad-release

CarPad（海豹07 DM-i 车机副屏）双 APK 在线更新发布源。

- `version.json` — 版本索引（双端版本号 / 下载路径 / SHA-256 / 更新说明）
- `apk/` — 按版本归档的双 APK（车机端服务端 + 平板端客户端）

更新链路：客户端/服务端拉取 `version.json` 比对 versionCode → 多镜像通道下载 APK → SHA-256 校验 → 安装（车机端静默 pm install，平板端系统安装确认）。

发布：`python tools/build.py --publish`（本地执行，自动计算哈希并推送本仓库）。
