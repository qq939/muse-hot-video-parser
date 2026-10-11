# 自托管部署指南

## Docker 部署

```bash
git clone https://github.com/Evil0ctal/Douyin_TikTok_Download_API.git
cd Douyin_TikTok_Download_API
docker compose up -d
```

启动后：
- Web 控制台：http://127.0.0.1:8000
- API 文档：http://127.0.0.1:8000/swagger
- MCP 接入点：http://127.0.0.1:8000/mcp/（需 API Key）

## API Key 获取
1. 打开控制台，用 admin 账号登录（首次启动时设置）
2. 进入 API Keys 页面，创建新 key（需要 `douyin:read` scope）
3. 调用时带 header：`Authorization: Bearer <key>` 或 `X-API-Key: <key>`

## 常用 API
- 解析视频：`POST /api/v1/douyin/fetch`，body: `{"url": "https://www.douyin.com/video/xxx"}`
- 查询任务状态、下载文件等见 `/swagger`

## MCP 接入
详见项目文档 `documents/en/12-mcp.md`。8 个只读工具，适合 AI agent 调用。
