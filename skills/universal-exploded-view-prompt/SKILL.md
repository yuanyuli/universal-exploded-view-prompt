---
name: universal-exploded-view-prompt
description: "Use when a user wants an exploded view, product infographic, e-commerce listing image, or explanatory visual that keeps one exact object consistent while explaining its components, features, use scenes, or assembly."
---

# 万能拆解图提示词

## 核心原则

把流程固定为：**结构真源 → 模式与风格 → 信息架构 → 拆解规格表 → 图生图提示词 → 后期标注 → 逐项验收**。

目标是“看懂一件东西”，不是把零件散开摆满画面。完整主体、组成清单、细节解释和使用方法要共同构成一张信息图。

“万物都可拆解”是编辑方向，不是事实承诺。没有参考图、产品资料或可核对的外部结构时，只能把结果称为概念图；不能把模型猜出的内部零件写成真实结构。

## 工作流程

### 1. 先判断输入模式

- 对象参考图：把它当作对象身份和外观真源，锁定轮廓、材质、颜色、视角和部件位置。
- 版式参考图：只学习信息架构、卡片分区、字体留白、细节放大和说明方式；不要把参考图里的文字、人物或装饰误当成目标对象事实。
- 结构参考图：用于核对真实部件和装配关系，不能替代对象参考图的外观。
- 没有参考图：先选结构简单、外部部件可见的对象；在输出中标明“概念拆解”，不要声称结构准确。
- 用户要求严格对应、说明用途或可分享：必须先做信息架构和规格表，再写提示词；不能先生成一张图再补规则。
- 先检查当前生成端点是否真的支持图片输入。如果端点只接受文字提示词，不能声称已经使用参考图；此时把结果标为“文本生成概念稿”，并把参考图职责转成文字约束。

### 2. 选择交付模式

根据用户要发布的位置选择模式，不能把所有内容塞进一张图：

| 模式 | 适合交付 | 核心规则 |
| --- | --- | --- |
| 知识拆解模式 | 公众号、社媒、科普长图 | 完整主体 + 组成 + 细节 + 方法/场景；信息密度优先 |
| 电商商品图模式 | 商品主图、卖点图、详情页 | 一张图只回答一个购买问题，主图突出商品，卖点图突出证据 |
| 混合详情页模式 | 电商详情页首屏到尾屏 | 先用商品主图建立身份，再用拆解、细节、场景和使用图完成说服 |

电商商品图模式默认规划为一组互相一致的资产，而不是一张拥挤海报：

1. **商品主图**：1:1 或平台要求的比例，主体居中、轮廓完整、背景干净；没有明确要求时不塞长段文字。
2. **卖点图**：4:5 或 3:4，只放 1–3 个可核对卖点和对应局部特写。
3. **结构拆解图**：4:5，展示组件、作用和对应位置；只拆外部可验证部件。
4. **场景图**：3:4 或 4:5，展示真实使用地点和尺度，不制造虚假评价或效果承诺。
5. **使用/养护图**：4:5 或长图，用步骤、注意事项和清洁方法解决购买后的疑问。
6. **参数/尺寸图**：只有用户提供尺寸、材质、容量或规格时才生成；缺数据就留空，不让模型猜。

同一组图必须锁定同一对象的轮廓、颜色、材质、部件数量、相机角度和比例。若没有实物参考图和商品资料，只能交付“概念商品图”，不能直接当作真实商品参数或性能证明。

### 3. 选择风格预设

先从风格库中选一个主风格，最多叠加一个辅助风格；不要每张图随意换色。详细参数见 [电商风格库](references/ecommerce-style-library.md)。

| 风格 | 视觉特征 | 更适合 |
| --- | --- | --- |
| 高级编辑风 | 暖象牙白、深墨绿、铜金细线、克制留白 | 家居、咖啡、出行、生活方式产品 |
| 纯净目录风 | 白/浅灰背景、均匀高光、少装饰、主体居中 | 主图、标准商品展示、配件类 |
| 深色奢华风 | 炭黑背景、低调金属光、局部高光 | 金属、数码、酒具、礼盒 |
| 自然生活风 | 米白、橄榄绿、柔和日光、真实桌面或户外 | 食品、家居、户外用品 |
| 技术精密风 | 冷灰、蓝色或青色辅助线、网格、等距视角 | 工具、器材、结构复杂的产品 |

风格不等于装饰。每次选定风格时同时锁定背景、光线、材质表现、线条颜色、卡片底色和字体层级，避免“高级感”只靠增加金色或阴影。

### 4. 先定信息架构

默认采用“完整主体 + 组成清单 + 细节放大 + 作用说明 + 使用场景/方法”的版式。按对象需要增减模块：

| 模块 | 要回答的问题 |
| --- | --- |
| 完整主体 | 这是什么，整体效果或使用状态是什么 |
| 组成清单 | 它由哪些可见元素组成 |
| 细节放大 | 哪些结构、材质、比例或工艺值得看 |
| 作用说明 | 每个元素解决什么问题，为什么放在这里 |
| 使用场景 | 适合什么人、地点、活动或搭配 |
| 使用方法 | 读者下一步怎么照着做、组合或维护 |
| 边界提示 | 哪些判断来自参考图，哪些只是概念建议 |

穿搭类可以对应为“穿搭关键词、今日穿搭、版型亮点、配饰重点、适合场景、配色解析、穿搭 Tips”；商品类可以对应为“商品构成、材质细节、功能解释、使用场景、购买/维护提示”。

电商模式额外回答四个购买问题：**这是什么、凭什么相信、怎么使用、是否适合我**。每一张图只承担其中一个主问题，其他信息通过同一套视觉系统衔接。

### 5. 写拆解规格表

每个部件都要有可核对的位置和证据。最少包含：

| 字段 | 要求 |
| --- | --- |
| 对象 | 名称、型号或“概念对象” |
| 视角 | 正视、三分之四、等距或剖面；左右视图必须相同 |
| 布局 | 完整主体、组成卡片、细节放大、说明区和留白位置 |
| 部件 | 编号、名称、装配位置、可见外观 |
| 证据级别 | A：照片可见；B：外部结构能合理推断；C：隐藏或虚构，禁止放入主图 |
| 对应关系 | 爆炸部件在装配图中的原始 x/y 位置 |
| 说明 | 每个部件的作用、搭配/使用理由、适用场景 |
| 标注 | 中文名称、用途、尺寸、颜色或警告由谁添加 |

一般先控制在 4–10 个核心部件，再补 3–6 个细节放大或特征说明。信息密度来自“部件 + 作用 + 场景/方法 + 对应位置”，不是来自增加空白圆圈。

### 6. 选择版式

- 信息图优先：让完整主体占主要视觉区域，组成清单和细节卡围绕主体排布；主爆炸图服务于说明，不要取代主体。
- 需要严格对齐时：采用“一个小装配缩略图 + 一个主爆炸图”，主图保留同一视角，并用淡色轮廓或定位线说明对应关系。
- 采用左右双图时：两边必须是同一相机、同一比例、同一基准线；右图只能沿一个轴分离部件。
- 需要展示剖面时：只剖开能被资料或照片证明的层，不自动补内部电路、螺丝和尺寸。
- 需要解释风格或组合时：把颜色、材质、比例、场景和 Tips 做成独立信息卡，不把它们藏在装饰里。

### 7. 生成图生图提示词

提示词必须明确参考图的职责，并重复几何不变量：

```text
Use the supplied object reference image as the source of truth for one exact object: [object].
Use the supplied layout reference only for information architecture: complete hero object,
component cards, detail close-ups, explanation blocks, use scenes, and practical tips.
Create a high-density explanatory infographic, not a random pile of parts. Keep the complete
object clearly visible. Reuse identical geometry, camera angle, scale, silhouette, material,
color, and part count. Show [component list] and separate only externally verifiable parts.
For each component, reserve a clear visual slot for: [name], [what it does], [why it matters],
and [where/how to use it]. Add detail close-ups for [feature list]. Each exploded part must
stay at the same x/y position it occupies in the assembled object and move only along [axis].
Use a clean editorial information-sheet layout, consistent spacing, readable hierarchy,
complete object hero, concise labels, believable materials, and phone-readable text areas.
```

电商模式提示词必须另外写清楚：

```text
Mode: e-commerce product image set
Asset role: [main product image / selling-point card / exploded structure card / scene card / usage-care card]
Platform and ratio: [1:1 / 4:5 / 3:4 / long detail image]
Product identity: keep the exact same object, geometry, material, color, and part count across the set.
Claim source: only use claims supplied by the user or directly visible in the reference; do not invent specs or performance.
Commercial composition: make the product the first visual read, keep text inside safe margins, and reserve clean space for later typography.
```

如果目标是商品主图，减少文字、道具和场景；如果目标是卖点图或详情页图，再增加局部特写、结构引线和使用说明。不要用“主图逻辑”生成一张信息塞满的详情页，也不要用“详情页逻辑”做一张失去商品识别度的主图。

### 8. 文字和后期标注

默认把标题、部件名、作用、场景和 Tips 作为后期排版文案，先给模型明确的文本槽位和信息层级。只有用户提供了逐字文案、模型具备可靠文字能力且画面确实需要内嵌文字时，才允许生成文字；生成后逐字核对，不把乱码当成完成。

### 9. 固定负面约束

始终检查并写入：`changed geometry, changed camera, mismatched proportions, invented internal parts, extra components, duplicate object, arbitrary rotation, missing part, random decoration, empty information blocks, unreadable text, fake logo, watermark, cropped object`。

如果采用后期排版模式，补充：`no pseudo-text, no random letters, no fake labels`。如果采用模型内嵌文字模式，改为“只允许以下逐字文本：……，禁止改写、漏字或新增文字”。

如果参考图本身看不清某个部件，提示词应写“do not reconstruct unseen details”，而不是要求模型补全。

电商模式补充：`no unverified claims, no fake specifications, no fake certification marks, no fake review, no price, no promotion badge, no platform logo, no misleading before-after effect`。

### 10. 后期标注和验收

模型负责形体、材质、构图和细节卡的视觉底稿；编号、中文名称、用途、尺寸、箭头、颜色卡、场景说明和 Tips 由 SVG、PIL、Figma 或排版工具后加。生成图里的文字不自动成为交付事实。

交付前逐项确认：

1. 完整主体和拆解元素是同一个对象，视角、比例和身份一致；
2. 每个组成卡或引线只指向一个部件，部件都能在主体中找到；
3. 每个部件都有名称、作用或组合理由，信息块不是装饰占位；
4. 细节放大确实来自参考图，场景和方法没有冒充真实测评；
5. 没有不可验证的内部结构或凭空增加的零件；
6. 文字、颜色、尺寸和图像位置互相对应；
7. 缩到手机宽度后，主体、部件层次、说明和 Tips 仍然清楚。

电商商品图再检查：

8. 商品主图在缩略图中仍能一眼认出商品，主体没有被文字、道具或裁切抢走。
9. 同一组图里的商品身份一致，没有颜色、材质、按钮、接口、部件数量漂移。
10. 每个卖点都有可见证据或用户提供的资料，不能只靠口号。
11. 平台比例、主体安全边距、文字安全区和底部裁切都符合交付尺寸。
12. 没有未经证实的容量、尺寸、材质、认证、防水、防火、抗风或医疗效果等承诺。

任一项不通过，就回到规格表或参考图，不用“再加一点细节”掩盖结构错误。

## 必须输出的格式

1. 对象判断与事实边界；
2. 交付模式、平台比例和风格预设；
3. 信息架构（主体、组成、细节、作用、场景、方法）；
4. 拆解规格表和卖点证据表；
5. 可直接复制的图生图提示词，电商模式按资产角色分别输出；
6. 负面约束；
7. 后期标注和文案方案；
8. 验收清单和可能失败点。

## 示例：摩卡壶

完整主体放右侧或上方，左侧/下方安排“组成清单”和细节卡：下壶体、滤斗、上壶体、翻盖与把手铰链；放大螺纹连接、滤孔板和安全阀；说明水、咖啡粉和成品咖啡分别经过哪里；最后给出清洗、炉具适配或使用场景。只有参考图能证明的结构才进入拆解图。

## 示例：折叠伞电商模式

同一把伞规划成一组商品图：商品主图只展示完整打开或收纳状态；卖点图展示伞面、伞骨和手柄的可见细节；结构图拆出伞面、伞骨、中棒、手柄、伞带与收纳袋；场景图展示通勤、旅行和雨天步行；使用图说明收纳、打开、撑开和晾干。没有真实产品资料时，不写防水等级、抗风等级、尺寸或材质参数。

## 红旗

- 先生成一张“看起来像”的图，再倒推结构；
- 把两张相似物品称为同一物品；
- 只把零件散开，却没有作用、场景或使用方法；
- 用空白圆圈数量代替信息密度；
- 让模型自由编写中文零件名称、尺寸或说明；
- 把模型猜出的隐藏结构写成真实资料。

出现这些情况时，停止生成，补齐参考图或规格表。
