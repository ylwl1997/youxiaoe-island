# 游小二的孤岛

You Xiaoe Island — 个人介绍静态网站，同时作为 **GitHub → Cloudflare Pages** 部署链路的测试站。

线上地址：<https://youxiaoe-island.pages.dev>

## 这是什么

一座界面简单干净的单页站点，展示个人简介、兴趣、示例作品与联系方式。页面文案统一来自 `src/data/profile.json`，作品条目为示例数据，用于验证构建与部署流程是否正常。

## 技术栈

- [Astro 5](https://astro.build/) — 零框架静态站点
- 纯 CSS（CSS 变量 + `prefers-color-scheme` 暗色/亮色）
- 系统字体栈，无外部 CDN 依赖

## 本地开发

```bash
npm install
npm run dev
```

浏览器打开终端提示的本地地址即可预览。生产构建：

```bash
npm run build
npm run preview
```

## 部署链路

```
push main → GitHub Actions → Cloudflare Pages（项目名 youxiaoe-island）
```

工作流文件：`.github/workflows/deploy.yml`

仓库需在 GitHub Secrets 中配置：

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

## 目录结构（简要）

```
src/
  data/profile.json    # 页面文案
  layouts/Base.astro   # HTML 骨架与 SEO
  pages/index.astro    # 首页
public/
  styles/global.css    # 全局样式
  favicon.svg
  robots.txt
  sitemap.xml
  _headers             # 静态资源缓存头
```
