# CardWorld Complete

Cloudflare Worker + D1 的可运行完整骨架，包含：隐藏管理员入口、卡密生命周期、同类型续期、5天宽限期、世界实例、角色/关系/通讯录、剧情消息、世界书、设置、种子库与管理后台。

## 本地运行
1. 安装 Node.js
2. `npm install`
3. `npx wrangler d1 create cardworld`
4. 把返回的 database_id 写入 `wrangler.toml`
5. `npx wrangler d1 execute cardworld --local --file=schema.sql`
6. `npx wrangler dev`

首次设置管理员密码：需要直接在 D1 中插入 `admin_settings`：
`INSERT INTO admin_settings(k,v) VALUES ('admin_password','你的管理员密码');`

部署：`npx wrangler deploy`，生产 D1 初始化使用 `npx wrangler d1 execute cardworld --remote --file=schema.sql`。

> 这是完整可运行工程骨架，AI 生成器/真实 TTS 供应商需在后续接入具体 API；当前剧情有无外部 AI 也能运行。
