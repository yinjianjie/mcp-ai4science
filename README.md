# MCP-AI4Science 部署安装方法

## 环境准备

1. 安装 [Python 3.8+](https://www.python.org/downloads/)
2. 安装 [uv](https://github.com/astral-sh/uv) 工具（推荐使用 pip 安装）：  
   ```bash
   pip install uv
   ```
3. 推荐使用 uv 自带的虚拟环境管理，无需单独安装 conda 或 virtualenv。

## 初始化项目

```bash
cd mcp-ai4science
uv init
```

## 创建并激活虚拟环境

```bash
uv venv
source .venv/bin/activate
```

## 安装依赖

```bash
uv add mcp arxiv
```

## 启动 Inspector

```bash
npx @modelcontextprotocol/inspector uv run research_server.py
```

## CherryStudio 配置方法

在 CherryStudio 的配置文件中添加如下内容：

```json
{
  "nh8pzTCKvztnvQWgzb42R": {
    "name": "MCP-ai4science",
    "type": "stdio",
    "description": "",
    "isActive": true,
    "registryUrl": "",
    "command": "uv",
    "args": [
      "--directory",
      "/localpath/mcp-demo/mcp-ai4science",
      "run",
      "-m",
      "research_server"
    ]
  }
}
```

请将 `/localpath/mcp-demo/mcp-ai4science` 替换为你的实际项目路径。

## 其他说明

- 如果遇到依赖安装或环境问题，请确保 uv 已正确安装，并使用 uv 的虚拟环境和依赖管理功能。
- 路径相关参数请根据你的实际项目目录进行调整。
- 更多 uv 命令和用法请参考 [uv 官方文档](https://github.com/astral-sh/uv)。

## examples 目录说明

`examples` 目录包含 MCP-ai4science 的运行示例，可参考其中的脚本和配置进行实际操作和测试。
