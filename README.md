# 卡路里追踪服务 Calorie Tracking

一款通过自然语言交互追踪每日卡路里摄入量的MCP服务器，提供餐食记录、每日总结、周报生成和食物搜索功能。
A MCP server that tracks daily calorie intake through natural language interaction, providing meal recording, daily summary, weekly report generation, and food search functions.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| add_meal | Log a meal with food items and calories |
| get_daily_summary | Get today's calorie intake summary |
| get_weekly_report | Get weekly calorie consumption report |
| search_food | Search for calorie information of a specific food |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659909635](https://mcp.xiaobenyang.com/inspector/1777316659909635)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659909635](https://mcp.xiaobenyang.com/inspector/1777316659909635)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "卡路里追踪服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659909635/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "卡路里追踪服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659909635/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "卡路里追踪服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659909635",
          },
          "transport": "stdio"
        }
      }
}

```
