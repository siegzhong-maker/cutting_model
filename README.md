# 剪辑 App 体验优化原型

静态 HTML 交互原型（单文件 [`index.html`](index.html)），可直接部署到 Vercel，无需构建步骤。

## 本地预览

```bash
open index.html
# 或
npx --yes serve .
```

## 部署到 Vercel

### 方式一：Git 连接（推荐）

1. 将仓库推送到 GitHub / GitLab / Bitbucket
2. 打开 [vercel.com](https://vercel.com) → **Add New Project** → 导入仓库
3. 保持默认即可：
   - **Framework Preset**: Other（或无框架）
   - **Build Command**: 留空
   - **Output Directory**: `.`（根目录）
4. 点击 **Deploy**

部署后访问根路径 `/` 即可。

### 方式二：Vercel CLI

```bash
npm i -g vercel
cd /path/to/Cutting_model-main
vercel          # 首次：登录并关联项目
vercel --prod   # 生产环境
```

## 项目说明

- **无需** `package.json` 或构建命令；Tailwind / Font Awesome 通过 CDN 加载
- 图片使用 Unsplash 外链，部署后需能访问外网
- 根目录 [`vercel.json`](vercel.json) 已配置 `cleanUrls` 与基础安全头

## 可选后续优化

- 将 Tailwind CDN 改为构建产物（更稳定、可离线）
- 将演示图片放到 `public/` 或对象存储，减少对外部 CDN 依赖
