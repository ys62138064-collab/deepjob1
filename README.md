# Deepjob · 求职 App 界面集（S1–S27）

一套 **无需构建、直接托管** 的静态展示站：收录 Deepjob 求职 App 的 27 个界面（390 × 870），
按求职流程分为 6 个章节，并保留原来的 **可点击交互原型**。

## 两种浏览方式

| 方式 | 入口 | 说明 |
| --- | --- | --- |
| 静态画廊 | `index.html` | 多页面导航、章节画廊、关键词搜索、单屏大图查看 |
| 交互原型 | `prototype.html` | 原站点的 `index.html` 交互原型：左侧选画面、右侧可直接操作 |

## 目录结构

```
.
├── index.html              # 站点首页：章节入口 + 原型介绍
├── prototype.html          # 交互原型（原 index.html，未改动其逻辑）
├── screen.html             # 单屏大图查看（?id=s11）
├── pages/
│   ├── all.html            # 全部 27 屏
│   ├── intro.html          # 01 开场与启动
│   ├── onboarding.html     # 02 登录与引导
│   ├── jobs.html           # 03 职位与搜索
│   ├── apply.html          # 04 申请与状态
│   ├── growth.html         # 05 对话与成长
│   └── profile.html        # 06 个人中心
├── assets/
│   ├── css/style.css       # 设计系统与全部样式
│   ├── js/data.js          # 唯一数据源（章节 + 界面清单）
│   ├── js/main.js          # 导航、画廊、查看器交互
│   ├── favicon.svg
│   ├── images/  svg/       # 交互原型使用的资源（原样保留）
├── images/                 # 27 张界面图（s01.png … s27.png）
├── .nojekyll               # 让 GitHub Pages 不做 Jekyll 处理
└── README.md
```

## 本地预览

```bash
cd 项目目录
python3 -m http.server 8000
# 打开 http://localhost:8000
```

## 部署到 GitHub Pages

```bash
git init
git add .
git commit -m "Deepjob UI kit showcase"
git branch -M main
git remote add origin https://github.com/<用户名>/<仓库名>.git
git push -u origin main
```

然后在仓库 **Settings → Pages**：Source 选 **Deploy from a branch**，Branch 选 **main / (root)**，保存即可。

## 新增 / 修改界面

1. 把新图放进 `images/`（保持 390 × 870 或相近比例）；
2. 打开 `assets/js/data.js`，在 `SCREENS` 中追加：

```js
{ id: 's28', no: '28', file: 'images/s28.png', title: '面试邀约', desc: '一句话说明。', section: 'apply' }
```

导航、章节卡片、画廊、查看器、上一张 / 下一张会自动同步。

## 说明

- 所有图片与原型中的企业、职位、人物均为虚构示例，仅供展示与演示。
- 原型中的 AI 建议与情绪支持文案均标注免责提示，不代表专业服务。
