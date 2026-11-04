# 百变玉米 · 循塑 100

一个手机端的可持续生活互动 demo：用「每日一题」把环保知识拆成每天 1 分钟的小动作，用「百变玉米」卡牌把行为记录变成可收集的成长轨迹。

在线浏览：<https://wintermoon123.github.io/baibianyumi/>

## 四个标签页

| 标签 | 内容 |
| --- | --- |
| 广场 | 品牌故事卡片（真实农户故事 + 示例故事）、商店试吃商品、可持续小知识 |
| 每日一题 | 每天一道可持续主题选择题，答对 +5 积分，可生成分享卡片 |
| 点子市集 | 按「身份视角」筛选的环保创意点子，附环保锦囊 |
| 我的 | 用户信息、积分/卡牌/答题统计、答题记录、我的卡牌、粉丝群二维码 |

## 本地运行

页面是单文件应用，无需构建、无需服务器：

```bash
# 直接双击 index.html 即可，或起一个静态服务
python3 -m http.server 8000
# 打开 http://localhost:8000
```

用户数据存在浏览器 `localStorage`（键名 `xunsu_user_v1`），清缓存即重置。

## 目录结构

```
index.html        单文件应用（HTML + CSS + JS + 二维码库全部内联）
corn-base.png     玉米角色立绘（透明底 PNG），用于头像与卡面
img/              内容配图，7 张实拍照片
.nojekyll         关闭 GitHub Pages 的 Jekyll 处理
```

## 技术说明

- 纯原生 HTML/CSS/JS，无框架、无打包工具、无外部 JS 依赖。
- 二维码生成库（qrcode-generator, MIT）已内联进 `index.html`。
- 分享卡片用 Canvas 2D 绘制：画布 720×960，内容超长时自动增高，导出 PNG。
- 字体走 Google Fonts（Noto Sans SC / Noto Serif SC），离线时回退系统字体。
- 视觉规范：森林绿 `#228B22`、大地棕 `#8B4513`、天蓝 `#87CEEB`、米色 `#F5F5DC`；圆角 16–24px；图标为内联 SVG 线性图标。

## 图片来源

`img/` 下 7 张照片来自 [Pexels](https://www.pexels.com)，遵循 [Pexels License](https://www.pexels.com/license/)（可免费用于商业与非商业用途，无需署名）：

| 文件 | 内容 | 来源 |
| --- | --- | --- |
| story-1.jpg | 农户手持玉米 | <https://www.pexels.com/photo/3307282/> |
| story-2.jpg | 编织篮 | <https://www.pexels.com/photo/24811442/> |
| story-3.jpg | 彩色观赏玉米 | <https://www.pexels.com/photo/1527005/> |
| prod-1.jpg | 观赏玉米（文玩） | <https://www.pexels.com/photo/33853176/> |
| prod-2.jpg | 手工编织篮 | <https://www.pexels.com/photo/28617395/> |
| prod-3.jpg | 糙米 | <https://www.pexels.com/photo/8108115/> |
| prod-4.jpg | 贴纸 | <https://www.pexels.com/photo/12413393/> |

替换正式素材时，覆盖同名文件即可，无需改代码（页面按 2.4:1 / 1.7:1 的比例裁切显示）。

## 说明

这是概念验证 demo：题目、故事、商品均为演示数据，购买流程与粉丝群二维码为占位，未接入真实支付与后台。
