# AI 产品经理学习资料

这是一份中文学习资料仓库，聚焦 `AI 应用产品经理`、`AI Agent 产品经理`、`AI 解决方案产品经理` 的能力建设。

当前已经整理成适合放在 GitHub 上阅读的公开文档形式，推荐按现在的学习顺序阅读：

- [Day 1：Prompt 设计与结构化输出](./study-packs/day1-prompt-structured-output-study-pack.md)
- [Day 2：RAG 与知识库产品设计](./study-packs/day2-rag-knowledge-base-study-pack.md)

## 适合谁

- 想从传统产品岗位转向 AI 产品方向的同学
- 需要系统理解 Prompt、结构化输出、评测与迭代方法的人
- 想把“会和模型对话”升级成“能做 AI 产品设计”的学习者

## 这份仓库有什么

- `study-packs/`: 按天拆分的学习包
- `README.md`: 仓库入口与导航

## 推荐阅读顺序

1. 从 Day 1 学习包开始，先建立 Prompt 与结构化输出的基础框架。
2. 接着看 Day 2，建立对 RAG、知识层和知识增强架构选型的判断。
3. 跟着文档里的练习完成第一版 Prompt、知识层设计和选型表。

## 内容说明

- 文档中的案例主要使用 `物流 / 订单评价 / 异常处理` 场景，方便练习 AI 产品中最常见的分类、建议生成和结构化交付问题。
- 这些案例是通用训练素材，不依赖公司内网、私有数据或内部系统。
- 你可以把示例场景替换成自己的业务领域继续复用。

## 发布到飞书文档

仓库里已经补了一个最小可用脚本，可以把本地 Markdown 发成飞书新版文档：

```bash
export FEISHU_APP_ID=你的飞书应用 App ID
export FEISHU_APP_SECRET=你的飞书应用 App Secret
python3 scripts/feishu_publish_markdown.py README.md
```

如果你想把文档创建到指定文件夹，也可以追加 `--folder-token`：

```bash
python3 scripts/feishu_publish_markdown.py \
  study-packs/day2-rag-knowledge-base-study-pack.md \
  --folder-token 你的文件夹 token
```

脚本会输出：

- 新建的 `document_id`
- 飞书文档标题
- 一个可直接打开的 `document_url`
- 本次写入的块数量

当前脚本支持的 Markdown 结构：

- `#` 到 `######` 标题
- 普通段落
- 无序列表、有序列表
- 引用
- 分割线
- 代码块

接入前请先在飞书开放平台给应用开通云文档相关权限，至少需要能：

- 获取 `tenant_access_token`
- 创建及编辑新版文档

说明：

- 凭据只从环境变量读取，不会写死在仓库里。
- `tenant_access_token` 创建文档时，如果传了 `folder_token`，通常只能写入应用自己可访问的文件夹。
