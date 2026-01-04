# Copilot 指南：lear-mysql

## 项目概览

本仓库是面向初学者的 MySQL 教学项目，内容以逐步递进的课时（lesson）组织，每个课时目录（例如 `lesson1/`, `lesson2/`）包含一个 `note.ipynb` 笔记本，笔记本中主要为可执行的 SQL 示例与中文讲解。

## 环境与依赖

- **Python 版本**：3.12（由 `.python-version` 管理）
- **依赖管理**：uv（锁文件 `uv.lock`）
- **运行环境**：JupyterLab（用于交互式执行 SQL）
- **数据库**：本地安装 MySQL（可通过 Homebrew 或官网下载）
- **推荐工具**：Beekeeper Studio（可视化管理数据库）

## 笔记本结构说明

- 单个 `note.ipynb` 包含混合语言单元：SQL 单元与 Python 单元。
- 所有注释与讲解均为**中文**。
- SQL 单元为可直接执行的 SQL 语句，**语句必须以分号结尾**。

示例（来自 `lesson1/note.ipynb`）：

```sql
CREATE TABLE helloworld(
  user_email VARCHAR(50), 
  user_id INT
);
```

## 关键开发/使用工作流

### 在笔记本中执行 SQL

- 确保 MySQL 服务已启动：`brew services start mysql`
- 确保存在并选中了数据库：`USE learn_mysql;`
- SQL 语句以 `;` 结束，否则不会执行完整语句

### 添加新课时

按现有目录格式添加新目录：

```
lessonN/
  note.ipynb  # 按同样风格加入示例与中文说明
```

## 项目特定约定

- 文档与注释统一为**中文**，新增内容请保持一致
- 笔记本中执行系统命令请放在 Python 单元并以 `!` 开头
- 每节课按顺序递进，后续课时可依赖前一课的表与数据

## 关键文件说明

- `pyproject.toml`：项目依赖（主要为 `jupyterlab`）
- `.python-version`：指定 Python 版本（3.12）
- `lessonN/note.ipynb`：课时内容的主要载体

## 协助本项目时的具体要求

- 新增笔记、示例或修正均用中文编写
- 提交的 SQL 示例须在 `learn_mysql` 数据库下可运行（包含 `USE learn_mysql;`）
- 若需运行说明或安装步骤，可在相应 `lesson` 的笔记本中添加演示单元
