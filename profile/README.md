# x-cmd-install

Daily activity snapshots for the software indexed by [`x install`](https://x-cmd.com/install).

Every repository in this organization corresponds to one package in the
[x-cmd/install](https://github.com/x-cmd/install) index. They are **not** mirrors of the
software — each one only carries a pointer to its upstream repository plus a folder of
dated snapshots:

```
<software>/
  README.md          # yfm frontmatter: owner-repo: <upstream owner>/<repo>
  data/260828.yml    # one snapshot per day
```

A snapshot records stars, watchers, forks, releases, contributors, language byte
breakdown, and activity counts over rolling 30 / 90 / 180 / 360-day windows (merged PRs,
open PRs, closed issues, open issues, commits, releases). All of it is aggregated into
[**x-cmd-install/x-cmd-install-stat**](https://github.com/x-cmd-install/x-cmd-install-stat).

## Everything here is generated — we don't accept pull requests

Each repository runs a scheduled GitHub Action once a day and commits its own snapshot.
Nothing in `data/` is written by hand, so a PR against these repositories would be
overwritten by the next run. Issues and PRs on the per-software repositories are not
monitored.

The collector is `x repo card`, a subcommand of the x-cmd `repo` module —
**<https://x-cmd.com/mod/repo>**. It reads entirely through the GitHub API (1 GraphQL
request plus 1 REST call per repository, no clone) and emits the YAML you see in `data/`:

```sh
x repo card jqlang/jq              # colored table on a TTY
x repo card jqlang/jq > card.yml   # bare YAML when piped or redirected
```

## Where to go instead

| If you want to… | Go to |
| --- | --- |
| add, correct, or remove a package | open an issue on [x-cmd/install](https://github.com/x-cmd/install/issues) |
| report wrong or missing data in a snapshot | open an issue on [x-cmd/install](https://github.com/x-cmd/install/issues) |
| extend what `x repo card` collects | send a PR to [x-cmd/x-cmd](https://github.com/x-cmd/x-cmd) |
| browse the package index | [x-cmd.com/install](https://x-cmd.com/install) |
| read the collector's docs | [x-cmd.com/mod/repo](https://x-cmd.com/mod/repo) |

---

# x-cmd-install（中文）

为 [`x install`](https://x-cmd.com/install) 索引收录的软件做每日活跃度快照。

本组织下每个仓库对应 [x-cmd/install](https://github.com/x-cmd/install) 索引里的一个软件，
**不是**软件本身的镜像 —— 只放一个指向上游仓库的指针，加上一个按日期归档的快照目录。

快照记录 star / watcher / fork / release / 贡献者数、语言字节构成，以及 30 / 90 / 180 /
360 天滚动窗口内的活跃度（合并的 PR、开启的 PR、关闭的 issue、开启的 issue、提交、发布）。
全部汇总到
[**x-cmd-install/x-cmd-install-stat**](https://github.com/x-cmd-install/x-cmd-install-stat)。

## 这里的内容全部自动生成，不接受 PR

每个仓库每天由 GitHub Action 定时跑一次，自己提交自己的快照。`data/` 下没有一个字节是手写的，
所以对这些仓库提 PR 会被下一次运行覆盖掉。各软件仓库的 issue 和 PR 都不做跟踪。

采集脚本是 `x repo card`，x-cmd `repo` 模块的子命令 —— **<https://x-cmd.com/mod/repo>**。
它全程走 GitHub API（每个仓库 1 次 GraphQL + 1 次 REST，不做 clone），输出的就是 `data/`
里的 YAML。

## 有想法请到这些地方

| 你想… | 去 |
| --- | --- |
| 增加、修正、移除某个软件 | 在 [x-cmd/install](https://github.com/x-cmd/install/issues) 开 issue |
| 反馈快照数据有误或缺失 | 在 [x-cmd/install](https://github.com/x-cmd/install/issues) 开 issue |
| 增强 `x repo card` 的采集内容 | 向 [x-cmd/x-cmd](https://github.com/x-cmd/x-cmd) 提 PR |
| 浏览软件包索引 | [x-cmd.com/install](https://x-cmd.com/install) |
| 查看采集脚本文档 | [x-cmd.com/mod/repo](https://x-cmd.com/mod/repo) |
