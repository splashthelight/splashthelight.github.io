# splashthelight.github.io

我的个人学术主页。基于 [LeoQLi.github.io](https://github.com/LeoQLi/LeoQLi.github.io)（它本身 fork 自 [keunhong.github.io](https://github.com/keunhong/keunhong.github.io)）改造。

模板版权：[Creative Commons BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/)

---

## 上线（部署到 GitHub Pages）

这套模板是 **Jekyll** 构建的，但**本地完全不需要安装 Ruby**——因为构建在 GitHub 云端自动完成，你本地只改文件 + `git push` 即可。

### 一、推送到 GitHub

确保仓库名是 `splashthelight.github.io`（大小写无所谓），然后：

```bash
git init
git add .
git commit -m "init my homepage"
git branch -M main
git remote add origin https://github.com/splashthelight/splashthelight.github.io.git
git push -u origin main
```

### 二、开启 GitHub Pages

1. 打开仓库 **Settings → Pages**
2. **Source** 选 **"Deploy from a branch"**
3. **Branch** 选 `main`，目录选 `/ (root)`，点 **Save**
4. 等 1~2 分钟，访问 **https://splashthelight.github.io/** 即可

之后每次 `git push` 都会自动重新构建发布。

---

## 要改哪些文件

| 文件 | 作用 |
|---|---|
| `_config.yml` | **最重要的**：你的名字、邮箱、简介、Google Scholar ID、GitHub 用户名、`url` |
| `_data/authors.yml` | 论文合著者信息（`is_me: true` 的是你自己，会自动加粗） |
| `_data/publications.yml` | 论文列表（详情见文件内注释） |
| `_data/news.yml` | 新闻动态 |
| `index.html` | 主页版式：姓名横幅、简介、News、Publications、Academic Service |
| `home/images/portrait.png` | **你的头像照片**（当前是占位图，覆盖同名文件即可） |
| `home/images/*.jpg` | 各论文的缩略图（按 publications.yml 里 image 字段命名） |

> 基本信息（名字、邮箱、职位、简介、研究方向、GitHub 用户名）我已经帮你填进 `_config.yml` 了。
> 你接下来只需要：
> 1. 把你的头像照片放到 `home/images/portrait.png`（覆盖同名占位图）
> 2. 往 `_data/publications.yml` 和 `_data/news.yml` 里填入你的论文和新闻
> 3. 以后有了 Google Scholar 账号，把 ID 填进 `_config.yml` 的 `google_scholar`

### 论文项目页（可选）

Leo 原模板里 `LGSF/`、`HSurf-Net/` 这种目录是单篇论文的独立项目主页（nerfies 风格）。我已删掉示例。以后要给你的某篇论文单独做项目页时：
1. 复制一份示例项目页骨架进来
2. 在 `_data/publications.yml` 的对应条目加 `project_page: "https://splashthelight.github.io/你的目录/"`

---

## 常见问题

**问：一定要装 Ruby/gem 才能改网站吗？**
答：不用。本地只改文件、push 到 GitHub；构建由 GitHub 云端完成。Ruby 只是在"本地预览效果"时才可选地需要，不预览就完全不用。

**问：push 后网站没变 / 白屏？**
答：过 1~2 分钟再刷新；仍不对就去仓库 **Actions** 标签页或 **Settings → Pages** 看构建日志，GitHub 会告诉你哪里报错（常见：YAML 语法错误、图片路径写错）。

**问：想自定义域名？**
答：买域名后，`Settings → Pages` 填域名，DNS 加一条 CNAME 指向 `splashthelight.github.io`。
