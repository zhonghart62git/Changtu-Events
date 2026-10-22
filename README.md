# 畅途活动站 · events.leadtheway.cn

赛事 / 考级 / 展演的活动页，独立于主站发布。

## 与主站的关系

| | 主站 | 活动站 |
|---|---|---|
| 域名 | `leadtheway.cn` | `events.leadtheway.cn` |
| 仓库 | `Changtu-Official-Website` | `Changtu-Events`（本仓库） |
| 负责 | 品牌 / 课程 / 机构合作 | 活动详情与报名 |

**共享设计系统，不复制。** 本仓库的页面用绝对 URL 引用主站样式：

```
https://leadtheway.cn/assets/site.css
https://leadtheway.cn/assets/site-v2.css
https://leadtheway.cn/assets/logo.png
```

改主站样式，活动站自动跟随（Pages CDN 缓存约 10 分钟）。
只有 `events.css` 是本仓库自己的。

## 内容从哪来

三个 HTML 由主站仓库的 `events/` 目录生成，脚本在主站仓库外：

```bash
python _ref/build_events_site.py
```

它会把 `../` 相对链接改写为指向 `leadtheway.cn` 的绝对地址，并把
canonical / og:url 改到 `events.leadtheway.cn`。

**所以：改内容改主站的 `official-site/events/`，然后重跑脚本、推本仓库。**
不要直接手改本仓库的 HTML —— 下次生成会被覆盖。

## 发布

```bash
git add -A && git commit -m "说明" && git push origin main
```

GitHub Pages 源：`main` 分支根目录，`CNAME` 已设为 `events.leadtheway.cn`。

DNS（DNSPod）：

| 主机 | 类型 | 值 |
|---|---|---|
| `events` | CNAME | `zhonghart62git.github.io` |

## 来源说明

活动信息整理自主办方与活动办公室已发布的官方推文，每页页脚标注来源。
时间、组别、收费与晋级规则以当期官方简章为准。
