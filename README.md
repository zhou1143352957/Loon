# Loon 配置仓库

个人 Loon 代理配置文件管理仓库。

## 目录结构

```
.
├── config/         # Loon 主配置文件
│   └── loon.conf
└── rules/          # 分流规则列表（被主配置引用）
    └── TikTok.list
```

## 使用方式

1. 编辑 `config/loon.conf`，将 `[Remote Proxy]` 中的 `订阅链接` 替换为你的机场订阅地址。
2. 将 `rules/` 下的规则文件托管到可访问的 HTTPS 地址（如 GitHub），在 `[Remote Rule]` 中添加引用，例如：

```
https://<托管地址>/TikTok.list, policy=🚀 策略选择, enabled=true
```

3. 在 Loon App 中导入 `config/loon.conf`。

## 规则文件说明

`rules/` 下的 `.list` 文件为 Loon 规则列表格式，每行一条规则，不含 policy，policy 在 `[Remote Rule]` 引用时指定。