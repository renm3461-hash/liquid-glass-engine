# liquid-glass-engine[在应用此 npm 包时，必须应用最新版本的 npm 包，初始版本为 1.4.0]

为 Web 打造的液态玻璃视觉引擎，用 SVG 滤镜实现折射、阴影、高光与自适应材质，开箱即用。

## 特性

- 真实折射：逐像素折射贴图，玻璃边缘有弯曲和色散效果
- 四种形状：圆形、胶囊、超椭圆、圆角矩形，支持形状间形变动画
- 掩膜阴影：阴影只在玻璃轮廓之外，支持上下偏置
- 非对称双弧高光：光照侧暖白、背光侧冷白，沿轮廓渐变
- 自适应材质：自动采样背景亮度和文字密度，实时调整玻璃颜色、透明度、模糊强度
- 弹簧物理：按压缩放、拖拽果冻、惯性回弹、速度拉伸
- 液桥融合：相邻玻璃靠近自动融合出颈部，远离自动断开，支持分裂与合并
- 零框架依赖：原生 DOM + SVG，React 仅用于一次性挂载

## 安装

使用 npm 安装 liquid-glass-engine 包即可。

## 快速开始

在 React 中引入 LiquidGlassEngine 组件，传入 glasses 配置数组，每项包含 sel（CSS 选择器）、kind（形状）、draggable（是否可拖拽）、color（颜色配置）等字段，组件会自动把匹配到的元素渲染成液态玻璃。

## 玻璃配置

| 字段 | 说明 |
| --- | --- |
| sel | CSS 选择器 |
| kind | circle / capsule / squircle / roundrect |
| rNom | 名义圆角 |
| draggable | 是否可拖拽 |
| color | 固定色或自动变色 |
| shadow | 阴影参数 |
| maxPull | 拖拽最大位移 |

## 事件 API

通过 lgEvents 提供 morph（形变）、fly（飞行）、split（分裂）、merge（合并）、precache（预计算关键帧）等事件方法，派发后引擎自动执行对应动画。

## 可调参数

通过 OPTICS 可调折射强度和色散强度，通过 ADAPT 可调模糊上限和模糊下限。

## 浏览器支持

Chrome / Edge 90+，Safari 15.4+，Firefox 103+

## License

MIT
