# 作品集网页 — 使用指南

## 如何打开

双击 `about1d.html` 文件，会自动在浏览器中打开。

---

## 页面交互

- **点击铁盒盖子** → 盖子向上抬起，露出盒内图标
- **再次点击盖子** → 盖子合上
- **点击图标** → 弹出文件夹窗口展示内容
- **右下角音乐按钮** → 播放/暂停背景音乐，调节音量

---

## 如何修改内容

用任意文本编辑器（记事本、VS Code 等）打开 `about1d.html`，找到 `<script>` 标签开头的 `SITE_DATA` 对象，修改对应文字即可。

### 修改图标图片

四个图标（个人简介、运营案例、策划案例、设计案例）都可以替换为你自己的图片：

```javascript
const SITE_DATA = {
  upperIcons: [
    {
      id: 'about',
      title: '个人简介',
      color: 'pink',
      iconImage: 'images/about-icon.jpg',  // ← 你的图标图片路径，留空则显示默认图标
      content: { ... }
    },
    // 其余三个同理
  ]
};
```

### 修改个人简介内容

```javascript
content: {
  title: '关于我',              // ← 弹窗标题
  description: '你好！...',     // ← 描述文字
  details: [                    // ← 列表内容
    '姓名：[你的名字]',
    '职业：[你的职业领域]',
    ...
  ],
  image: 'images/photo.jpg'     // ← 个人照片路径
}
```

### 修改运营/策划/设计案例（纯图片展示）

这三个文件夹只展示图片，无文字描述：

```javascript
{
  id: 'ops',
  title: '运营案例',
  iconImage: 'images/ops-icon.jpg',
  content: {
    title: '运营案例',
    images: [
      'images/ops1.jpg',
      'images/ops2.jpg',
      'images/ops3.jpg'
      // ... 可以放任意多张
    ]
  }
}
```

### 修改背景音乐

```javascript
music: {
  file: 'audio/bgm.mp3',   // ← 音乐文件路径，留空则不播放
  name: '背景音乐',
  volume: 0.3              // ← 默认音量 0~1（0.3 = 30%，建议不要太大）
}
```

---

## 如何放入图片

1. 将图片文件放入 `images/` 文件夹
2. 在 `SITE_DATA` 对应项填写路径，例如：`'images/作品1.jpg'`
3. 图标图片建议使用正方形图片（会自动裁剪为圆形）

---

## 如何放入音乐

1. 将音乐文件（mp3 格式）放入 `audio/` 文件夹
2. 在 `SITE_DATA` → `music` → `file` 填写路径，例如：`'audio/bgm.mp3'`
3. 页面打开后自动循环播放（浏览器可能要求先点击页面任意位置）

---

## 文件夹结构

```
作品集/
├── about1d.html    ← 主页面（修改内容只需要编辑这个文件）
├── images/       ← 放你的图片
├── audio/        ← 放你的音乐
└── README.md     ← 本说明文件
```
