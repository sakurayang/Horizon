---
layout: default
title: "Horizon Summary: 2026-06-21 (ZH)"
date: 2026-06-21
lang: zh
---

> 从 55 条内容中筛选出 17 条重要资讯。

---

1. [Bun 通过大型 Pull Request 提议为 JavaScriptCore 添加共享内存线程支持。](#item-1) ⭐️ 8.0/10
2. [Cloudflare 推出临时账户，支持 AI 智能体和开发者进行临时部署](#item-2) ⭐️ 8.0/10
3. [SpaceX IPO 文件披露计划，拟在太空部署 AI 数据中心以突破地球电力限制。](#item-3) ⭐️ 8.0/10
4. [SMPTE 宣布其全部标准库免费向公众开放](#item-4) ⭐️ 7.0/10
5. [CSSQuake：一款完全使用 CSS 渲染的经典游戏《雷神之锤》复刻版](#item-5) ⭐️ 7.0/10
6. [上海海底数据中心通过海上风电实现 95%绿电和 1.15 的 PUE](#item-6) ⭐️ 7.0/10
7. [上交所发布大模型企业科创板上市指引，Anthropic 因美国出口管制关停两款最新模型访问。](#item-7) ⭐️ 7.0/10
8. [李在镕押注 AI 存储，在创纪录利润中重塑三星半导体帝国](#item-8) ⭐️ 7.0/10
9. [UHF X11 将 X11 窗口系统移植到 Apple VisionOS，适配 Vision Pro](#item-9) ⭐️ 6.0/10
10. [AI 助长《The Dictionary of Obscure Sorrows》整体抄袭，凸显平台执法失效。](#item-10) ⭐️ 6.0/10
11. [界面工程策略构筑高输出、全可拉伸湿气发电机。](#item-11) ⭐️ 6.0/10
12. [研究揭示 AI 可能导致技能退化，挪威出台教育限制政策](#item-12) ⭐️ 6.0/10
13. [挪威将于 2026 年新学年起禁止小学生使用生成式 AI，并对中学生实施分级限制。](#item-13) ⭐️ 6.0/10
14. [读者与创作者日益重视 2022 年前的书籍与信息，因其感知可信度更高。](#item-14) ⭐️ 5.0/10
15. [《F-15 Strike Eagle II》DOS 游戏逆向工程寻求测试员，进行 DOS 到 C 语言的转换。](#item-15) ⭐️ 5.0/10
16. [StartupWiki 作为 Crunchbase 的免费开源替代品发布。](#item-16) ⭐️ 5.0/10
17. [AICon 上海大会专题演讲：探讨大模型驱动的银行信贷全链路变革](#item-17) ⭐️ 5.0/10

---

<a id="item-1"></a>
## [Bun 通过大型 Pull Request 提议为 JavaScriptCore 添加共享内存线程支持。](https://github.com/oven-sh/WebKit/pull/249) ⭐️ 8.0/10

一个大型的 Pull Request（#249）已被提交，旨在为 Bun 所使用的 JavaScript 引擎 JavaScriptCore 添加共享内存线程支持。该 PR 引入了一个新的 `Thread(fn)` 原语，允许闭包在共享同一 JavaScript 堆的情况下，在独立的操作系统线程上运行。 这代表了 JavaScript 架构的一次重大转变，超越了 Web Workers 和 SharedArrayBuffer 的限制，实现了真正的、低开销的并发执行。如果成功，它将为计算密集型应用带来新的性能水平，并可能影响整个 JavaScript 生态系统对并行处理的思路。 该 PR 是对一篇名为《Concurrent JavaScript: It Can Work!》的 WebKit 博客文章中所概述设计的实现。值得注意的是，这个 PR 规模很大（影响约 1800 个文件），并且据报道是借助 AI 辅助创建的，这已成为社区内讨论和质疑的一个焦点。

hackernews · gr4vityWall · 6月20日 17:02 · [社区讨论](https://news.ycombinator.com/item?id=48610841)

**背景**: JavaScript 传统上是单线程的，通过事件循环处理并发。Web Workers 允许并行执行，但通过消息传递进行通信，对于大数据传输可能较慢。SharedArrayBuffer 允许在线程间共享内存，但需要使用 Atomics 进行仔细的同步，并且受到安全限制。JavaScriptCore 是 Apple 为 Safari 开发的 JavaScript 引擎，也是 Bun 运行时背后的引擎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://byteiota.com/bun-new-thread-javascript-multithreading/">Bun's new Thread () PR: JS Gets True Multithreading | byteiota</a></li>
<li><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer">SharedArrayBuffer - JavaScript | MDN - MDN Web Docs</a></li>
<li><a href="https://bun.sh/">Bun — A fast all-in-one JavaScript runtime</a></li>

</ul>
</details>

**社区讨论**: 社区情绪复杂，对该技术提案有浓厚兴趣，但对其实现方式存在显著质疑。主要担忧包括由单个人监督的大型 AI 辅助 PR 的可信度，以及对 AI 生成的多线程代码质量的怀疑。作者澄清该 PR 实现的是一个现有的 WebKit 设计，一些评论者则对这一潜力表示兴奋。

**标签**: `#javascript`, `#concurrency`, `#runtime`, `#systems-programming`, `#web-development`

---

<a id="item-2"></a>
## [Cloudflare 推出临时账户，支持 AI 智能体和开发者进行临时部署](https://blog.cloudflare.com/temporary-accounts/) ⭐️ 8.0/10

Cloudflare 推出了一项名为“临时账户”的功能，允许 AI 智能体或开发者使用命令 `wrangler deploy --temporary` 临时部署一个 Cloudflare Worker，有效期为 60 分钟。这个临时部署后续可以被认领，从而将临时账户转换为永久账户。 这显著降低了测试和实验的门槛，实现了诸如自动化 PR 预览等新工作流，并允许 AI 智能体自主配置和部署无服务器应用。这标志着在无服务器和边缘计算生态系统中，向更自主、由智能体驱动的开发和部署周期迈出了一步。 如果未被认领，临时部署会在 60 分钟后自动过期。Cloudflare 对创建临时预览账户实施了速率限制，并应用了额外的防滥用检查，以减轻可能被用于托管恶意内容的风险。

hackernews · farhadhf · 6月20日 11:19 · [社区讨论](https://news.ycombinator.com/item?id=48608394)

**背景**: Cloudflare Workers 是一个无服务器平台，允许开发者在 Cloudflare 的边缘网络上全局部署代码，而无需管理服务器。AI 智能体是能够执行编码和部署等任务的自主程序。`wrangler` CLI 是用于开发、构建和部署 Cloudflare Workers 的官方工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.cloudflare.com/workers/platform/claim-deployments/">Claim deployments (temporary accounts) · Cloudflare Workers docs</a></li>
<li><a href="https://www.startuphub.ai/ai-news/technology/2026/cloudflare-s-ai-agent-account-shortcut">Cloudflare's AI Agent Account Shortcut | StartupHub.ai</a></li>

</ul>
</details>

**社区讨论**: 社区反应总体积极，强调了该功能对于 PR 预览和作为免费临时部署工具的实用性。提出的主要关切点包括需要设置硬性账单上限以防止意外费用，以及关于 Cloudflare 计划如何防止滥用临时基础设施托管恶意内容的问题。还有一位用户批评其营销文案明显是 AI 生成的。

**标签**: `#cloudflare`, `#serverless`, `#ai-agents`, `#devops`, `#edge-computing`

---

<a id="item-3"></a>
## [SpaceX IPO 文件披露计划，拟在太空部署 AI 数据中心以突破地球电力限制。](https://www.cyzone.cn/article/837210.html) ⭐️ 8.0/10

SpaceX 在其 IPO 文件中估算其总潜在市场高达 28.5 万亿美元，其中超过 90%来自 AI 领域，并提出通过将数据中心部署到太空中来规避地球发电能力的限制。埃隆·马斯克公布了 AI-1 卫星的设计草图，称其关键技术已在星链 V3 卫星中实现，并预计到 2027 年底实现每年部署 1 吉瓦太空 AI 算力的目标。 这一提议代表了 AI 基础设施战略的根本性转变，旨在解决未来大规模算力扩张所面临的电力供应关键瓶颈。如果可行，它将为 AI 发展解锁前所未有的规模，并建立一个可持续的、地球外计算基础设施的新范式。 实现 1 吉瓦的太空算力需要发射大约 10,000 颗 AI 卫星，相当于进行约 100 次星舰发射，其经济可行性取决于发射成本能否降至每公斤 200 美元以下。主要技术障碍包括：受黑体辐射定律制约的真空散热问题、GPU 阵列易受宇宙辐射影响的风险，以及轨道碎片碰撞可能引发凯斯勒效应的威胁。

rss · 最新资讯 - 创业邦 · 6月20日 09:28

**背景**: 作为技术基础的 SpaceX 星链 V3 卫星专为近地轨道设计，在带宽和激光回程容量上有显著提升。轨道数据中心是一种提议在太空建设的计算设施，它面临独特的发电和热管理挑战，因为与地球不同，热量无法通过对流散失，只能通过辐射散发，这受斯蒂芬-玻尔兹曼定律制约。这一概念旨在应对日益增长的担忧，即 AI 训练所需的指数级电力需求可能超过地球上新建发电厂的能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.allthings-elon.com/articles/starlink-v3-satellites-100x-bandwidth-starship-late-2026">Starlink V3 Satellites: 100x Bandwidth, 350km Orbit, Starship ...</a></li>
<li><a href="https://satnews.com/2026/03/17/the-physics-wall-orbiting-data-centers-face-a-massive-cooling-challenge/">The "Physics Wall": Orbiting Data Centers Face a Massive Cooling ...</a></li>
<li><a href="https://mlq.ai/news/spacex-unveils-ai1-orbital-data-center-satellite-targets-1-gw-space-compute-by-late-2027/">SpaceX Unveils AI1 Orbital Data Center Satellite, Targets 1 GW Space Compute by Late 2027 | MLQ News</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#AI Infrastructure`, `#Edge Computing`, `#Satellite Technology`, `#Sustainable Computing`

---

<a id="item-4"></a>
## [SMPTE 宣布其全部标准库免费向公众开放](https://www.smpte.org/blog/smpte-makes-its-standards-freely-accessible-openingstandards-library-to-the-global-media-technology-community) ⭐️ 7.0/10

2026 年 6 月 17 日，SMPTE 宣布其全部已发布标准目录现可免费供全球媒体技术社区使用。此举移除了此前访问其 800 多份技术标准文档的付费门槛。 这一决定显著降低了开发者、初创公司和教育机构的准入门槛，有望加速媒体技术行业的创新并增强互操作性。这符合开放标准的更广泛趋势，类似于 IETF 的模式，该模式历来推动了技术的广泛采用和进步。 此次免费开放是 SMPTE 更广泛的现代化进程的一部分，其中包括采用基于 GitHub 的工作流进行版本控制和问题追踪。该标准库包含关于彩条测试图、时间码、定时文本和数字影院等标志性标准。

hackernews · zdw · 6月20日 17:01 · [社区讨论](https://news.ycombinator.com/item?id=48610827)

**背景**: SMPTE（电影与电视工程师协会）是一个国际公认的标准组织，已为广播、电影制作和数字影院发布了 800 多项技术标准。这些标准是媒体技术互操作性的基础，确保不同供应商的设备和软件能够无缝协作。此前，许多此类关键技术文档需要购买，这可能会阻碍独立开发者和小型公司的访问。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.smpte.org/digital-library">Digital Library - Society of Motion Picture and Television Engineers</a></li>
<li><a href="https://www.smpte.org/blog/smpte-makes-its-standards-freely-accessible-openingstandards-library-to-the-global-media-technology-community">SMPTE Makes Its Standards Freely Accessible, Opening Standards Library to the Global Media Technology Community</a></li>
<li><a href="https://en.wikipedia.org/wiki/Society_of_Motion_Picture_and_Television_Engineers">Society of Motion Picture and Television Engineers - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 社区反应 overwhelmingly 积极，用户们庆祝这一长期障碍的消除。评论者将此与 IETF 免费标准的成功相提并论，并分享了之前为项目不得不购买标准的个人经历。也有人认识到，此举支持了新媒体制作和分发方式正在发生的爆炸性发展。

**标签**: `#standards`, `#open-access`, `#media-technology`, `#interoperability`

---

<a id="item-5"></a>
## [CSSQuake：一款完全使用 CSS 渲染的经典游戏《雷神之锤》复刻版](https://cssquake.com/) ⭐️ 7.0/10

一位开发者创建了 CSSQuake，这是一个完全可玩的经典第一人称射击游戏《雷神之锤》的复刻版，它使用 CSS 进行 3D 渲染，而非传统的游戏引擎或 WebGL。这个技术演示展示了非常规地使用 Web 技术来渲染复杂的 3D 游戏环境。 该项目作为一个概念验证具有重要意义，它突破了 CSS（一种主要用于网页样式设计的语言）的能力边界，突显了 Web 平台技术被忽视的创造性和潜力。它引发了关于性能、Web 标准演进以及轻量级、非常规游戏开发方法潜力的讨论。 该实现似乎是用 JavaScript 完整复刻了游戏的引擎和逻辑，而 CSS 负责视觉渲染，尽管部分游戏机制与原版不同（例如，有些按钮需要射击而非触碰才能激活）。尽管取得了技术成就，但其性能明显低于 90 年代在同期硬件上运行的原版游戏，并且该项目仍然需要 JavaScript 才能运行。

hackernews · msalsas · 6月20日 10:49 · [社区讨论](https://news.ycombinator.com/item?id=48608223)

**背景**: 《雷神之锤》由 id Software 于 1996 年发布，是一款具有里程碑意义的第一人称射击游戏，以其由专有 Quake 引擎驱动的全 3D 实时多边形图形而闻名。CSS（层叠样式表）是一种用于样式化和布局 HTML 文档的核心 Web 技术，虽然它包含用于创建透视和深度的 3D 变换属性，但它并非像专用游戏引擎或 WebGL 那样为实时、交互式 3D 图形渲染而设计。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quake_engine">Quake engine - Wikipedia</a></li>
<li><a href="https://www.tutorialpedia.org/blog/3d-games-with-just-css-and-html/">Creating 3D Games with Just CSS and HTML - tutorialpedia.org</a></li>

</ul>
</details>

**社区讨论**: 社区反应混合了对技术成就的钦佩和对其实用局限性的观察。评论者赞扬了其创造性和成就，其中一人称这是很久以来第一个真正让他们在网上感到开心的事情。然而，其他人指出了与原版游戏相比显著的性能问题，并注意到它仍然依赖 JavaScript，从而对“纯 CSS”的前提提出了质疑。还有一些人观察到了游戏机制与原版《雷神之锤》的不同之处。

**标签**: `#CSS`, `#Web Development`, `#Game Development`, `#Technical Demo`, `#Hacker News`

---

<a id="item-6"></a>
## [上海海底数据中心通过海上风电实现 95%绿电和 1.15 的 PUE](https://weekly.caixin.com/2026-06-20/102455832.html) ⭐️ 7.0/10

上海临港新片区的一个“算电协同”试点项目部署了由 50 余台海上风机直连供电的海底数据中心，实现了 95%的绿电比例和 1.15 的超低电源使用效率值。海兰云海底数据中心的一期项目已于今年 2 月陆续投入商用，二期项目计划在 2026 年内开工。 该项目通过将可再生能源发电与高耗能的计算设施直接结合，为可持续计算基础设施迈出了重要且务实的一步，这对于减少快速增长的 AI 和数据中心行业的碳足迹至关重要。它作为“算电协同”的先驱模型，这是中国一项旨在优化数字经济能源使用的关键政策举措。 该数据中心位于水下 10 米处的圆柱形舱体内，利用海水进行自然冷却，这是其实现超低 PUE 值的主要原因。报道的 1.15 的 PUE 值效率极高，因为行业平均水平通常在 1.5 到 1.7 之间，这表明几乎所有电力都用于计算，而用于冷却和其他支持系统的开销极低。

rss · 财新网 - 首页 · 6月20日 23:58

**背景**: 电源使用效率是衡量数据中心能源效率的关键指标，计算的是总设施能耗与 IT 设备能耗的比率；PUE 为 1.0 代表完美效率。海底数据中心是一个新兴概念，利用海水进行免费高效的冷却，解决了传统设施中的一个主要成本和能源消耗问题。“算电协同”是一个战略框架，在中国 2026 年政府工作报告中首次提出，旨在将电力供应网络与算力中心的位置和运营进行协同优化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Power_usage_effectiveness">Power usage effectiveness - Wikipedia</a></li>
<li><a href="https://news.samsungcnt.com/en/features/engineering-construction/2024-08-data-center-cooling-is-the-future-underwater/">Data Center Cooling: Is the Future Underwater?</a></li>
<li><a href="https://grokipedia.com/page/Computing-power_electricity_coordination">Computing-power electricity coordination — Grokipedia</a></li>

</ul>
</details>

**标签**: `#Green Computing`, `#Data Centers`, `#Sustainable Tech`, `#Edge Computing`, `#Energy Efficiency`

---

<a id="item-7"></a>
## [上交所发布大模型企业科创板上市指引，Anthropic 因美国出口管制关停两款最新模型访问。](https://www.caixin.com/2026-06-20/102455966.html) ⭐️ 7.0/10

6 月 17 日，上海证券交易所正式发布指引，明确人工智能大模型企业可适用科创板第五套上市标准，要求企业至少有一个大模型产品已完成上线并实现规模化应用。同日，美国 AI 公司 Anthropic 于 6 月 13 日发布公告，为遵守美国政府新的出口管制规定，突然面向所有客户关停了其两款最新编程大模型 Fable 5 和 Mythos 5 的访问权限。 上交所的新指引为资金密集型的中国大模型企业提供了明确的关键融资渠道，可能加速国内 AI 产业的发展与竞争力。Anthropic 的合规举措凸显了 AI 技术领域地缘政治分裂的加剧，出口管制直接影响了全球开发者对前沿工具的获取。 上交所的指引明确，发行人的主营业务须为人工智能大模型的自主研发、模型服务或模型应用，并且支持通用大模型和行业专用模型同步适用。Anthropic 的关停仅针对 Fable 5 和 Mythos 5 这两款据称在软件工程等领域具有更长自主工作能力的最新模型，该公司的其他所有模型仍可正常使用。

rss · 财新网 - 首页 · 6月20日 13:10

**背景**: 科创板是中国为高新技术和战略性新兴产业公司设立的股票交易板块，其上市标准更为灵活。其中的“第五套上市标准”是针对具有高成长潜力但可能尚未盈利或未产生收入企业的关键上市通道，此前已扩展至商业火箭等领域。Anthropic 是一家总部位于美国的领先 AI 安全与研究公司，Fable 5 和 Mythos 5 是其近期发布的、在编程和知识工作方面具有更强自主能力的高级模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://jrj.sh.gov.cn/SC212/20260618/6eb0dadf4a1e4a24a1dcb924316cef12.html">上交所发布人工智能大模型企业适用科创板第五套上市标准审核指引_中共上海市委金融委员会办公室、中共上海市金融工作委员会</a></li>
<li><a href="https://www.anthropic.com/news/claude-fable-5-mythos-5">Claude Fable 5 and Claude Mythos 5 \ Anthropic</a></li>
<li><a href="https://www.cnbc.com/2026/06/12/anthropic-disables-access-to-fable-5-and-mythos-5-to-comply-with-government-directive.html">Anthropic disables access to Fable 5, Mythos 5 on ... - CNBC</a></li>

</ul>
</details>

**标签**: `#AI Regulation`, `#Financial Markets`, `#Large Language Models`, `#Tech Policy`, `#Anthropic`

---

<a id="item-8"></a>
## [李在镕押注 AI 存储，在创纪录利润中重塑三星半导体帝国](https://database.caixin.com/2026-06-20/102455941.html) ⭐️ 7.0/10

2026 年第一季度，三星电子交出盈利空前的成绩单，单季营业利润同比暴涨 756%，半导体业务独揽集团 94%的收益。这一业绩不仅是行业周期的馈赠，更是三星会长李在镕多年来押注 AI 存储等半导体布局的阶段性兑现。 这标志着三星正进行战略转向，押注蓬勃发展的 AI 基础设施需求，旨在成为全球 AI 算力竞赛和供应链博弈中的关键参与者。此举若成功，可能重塑存储芯片市场的竞争格局，并巩固韩国在全球科技供应链中的地位。 李在镕的领导风格以低调务实著称，他将精力集中于产业布局而非个人曝光。创纪录的利润是在复杂的公众认知下取得的：他既被视为不可或缺的产业领袖，也被看作是韩国备受争议的财阀世袭垄断体系的象征。

rss · 财新网 - 首页 · 6月20日 13:05

**背景**: 半导体行业以其由库存动态和需求波动驱动的显著繁荣与萧条周期而闻名。AI 存储指的是专为 AI 和机器学习工作负载的海量数据集、高速访问和密集计算需求而优化的数据存储系统，这些数据越来越多地存储在数据中心的大容量硬盘上。三星是全球存储芯片的领导者，而存储芯片是计算和数据存储的关键组件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.seagate.com/innovation/ai/storage-and-compute-infrastructure/">Data Storage for AI | Seagate US</a></li>
<li><a href="https://ibinterviewquestions.com/guides/tmt-investment-banking/semiconductor-business-cycle">The Semiconductor Business Cycle | TMT IB Guide</a></li>
<li><a href="https://www.ibm.com/think/topics/ai-storage">What is AI Storage? | IBM</a></li>

</ul>
</details>

**标签**: `#Semiconductors`, `#Artificial Intelligence`, `#Business Strategy`, `#Supply Chain`, `#Geopolitics`

---

<a id="item-9"></a>
## [UHF X11 将 X11 窗口系统移植到 Apple VisionOS，适配 Vision Pro](https://www.lispm.net/apps/uhf-x11/) ⭐️ 6.0/10

UHF X11 是一款专为 visionOS 开发的原生 X11 服务器，于 2026 年 6 月 20 日发布。它使得经典的 Unix 和 Linux 应用程序能够在 Apple Vision Pro 头显的空间窗口中运行。 该项目创造性地将数十年前的桌面软件与前沿的空间计算连接起来，可能延长传统 X11 应用的生命周期。它展示了 X11 协议的灵活性，并为开发者和爱好者在新兴的 AR/VR 环境中使用熟悉的工具开辟了一个小众领域。 该服务器支持 OpenGL 客户端通过 X11 使用 GLX 渲染，但兼容性可能有所不同。它可以运行 TWM 等经典窗口管理器，将 Vision Pro 变为一个完整的 X11 显示服务器，但这是一个非官方的第三方实现，不受苹果官方支持。

hackernews · zdw · 6月20日 17:04 · [社区讨论](https://news.ycombinator.com/item?id=48610853)

**背景**: X Window System (X11) 是一个用于位图显示的网络透明的窗口系统，历史上在 Unix 和 Linux 上占主导地位。它具有高度的可移植性，已通过第三方服务器移植到各种操作系统。visionOS 是苹果为 Vision Pro 开发的扩展现实操作系统，衍生自 iPadOS，专为空间计算设计，其原生应用基于 RealityKit 等框架构建。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ad-hoc-news.de/wissenschaft/uhf-x11-unix-apps-jetzt-nativ-auf-apple-vision-pro/69593384">UHF X11: Unix-Apps jetzt nativ auf Apple Vision Pro</a></li>
<li><a href="https://en.wikipedia.org/wiki/X_Window_System">X Window System - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/VisionOS">visionOS - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论强调了该项目的新颖性和技术深度，用户指出在 3D 头显中通过 2D 的 X11 运行 3D OpenGL 颇具幽默感。有人将其与专注于 Linux 的 WayVR 项目进行比较，也有人推测 X11 可能比 visionOS 更长寿。还有一位用户寻求能适配处方镜片的 Linux AR 头显推荐。

**标签**: `#X11`, `#VisionOS`, `#Apple Vision Pro`, `#Windowing Systems`, `#AR/VR`

---

<a id="item-10"></a>
## [AI 助长《The Dictionary of Obscure Sorrows》整体抄袭，凸显平台执法失效。](https://waxy.org/2026/06/the-wholesale-plagiarism-of-obscure-sorrows/) ⭐️ 6.0/10

一篇文章详细披露，一个名为 Qontour 的网站（由 Prompt Digital Inc. 运营）逐字复制了 John Koenig 所著《The Dictionary of Obscure Sorrows》一书的全部文本，很可能是先用 AI 创建粉丝网站框架，然后粘贴了受版权保护的内容。创作者试图通过向谷歌和苹果发送 DMCA 通知来删除侵权内容，但据报道，在没有法院命令的情况下，这些努力收效甚微。 这个案例展示了 AI 工具如何大幅降低大规模版权侵权的成本和精力，使得整体抄袭变得更加普遍。它凸显了当受避风港条款保护的主要平台不愿对下架请求采取行动时，个体创作者所面临的严峻实践与法律挑战，迫使他们进行昂贵的法律诉讼。 此次抄袭并非意译版本，而是对书中所有 311 个新词及其序言的完整、逐字复制。文中提到的一个关键障碍是，像谷歌和苹果这样的平台通常要求提供正式的法院命令来处理针对应用商店列表或搜索结果的 DMCA 投诉，而不是仅根据通知本身进行仲裁。

hackernews · ridesisapis · 6月20日 18:05 · [社区讨论](https://news.ycombinator.com/item?id=48611411)

**背景**: 《数字千年版权法案》（DMCA）提供了一个“通知-删除”流程，版权持有人可以要求在线服务提供商移除侵权材料。遵守特定要求（如指定接收通知的代理人）的服务提供商通常受“避风港”规则保护，可免于承担责任。“整体抄袭”（Wholesale plagiarism）或“完全抄袭”（global plagiarism）指的是将他人的整个作品当作自己的作品进行呈现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://copyrightalliance.org/education/copyright-law-explained/the-digital-millennium-copyright-act-dmca/dmca-notice-takedown-process/">DMCA Notice & Takedown Process | Copyright Alliance</a></li>
<li><a href="https://undetectable.ai/blog/what-is-global-plagiarism/">What is Global Plagiarism ?</a></li>

</ul>
</details>

**社区讨论**: 评论者分享了类似的人工智能改头换面式盗窃的个人经历以及对平台执法的沮丧。一个关键的讨论点是，虽然 AI 降低了侵权成本，但根本问题在 AI 出现之前就已存在，包括企业匿名性以及盗窃与执法之间固有的不对称性。一些人指出此案是 DMCA 下架的典型案例，而另一些人则对一部受欢迎的作品被复制成一个更成功的山寨品表示讽刺。

**标签**: `#AI Ethics`, `#Plagiarism`, `#Intellectual Property`, `#DMCA`, `#Content Moderation`

---

<a id="item-11"></a>
## [界面工程策略构筑高输出、全可拉伸湿气发电机。](http://blog.sciencenet.cn/blog-3411509-1539715.html) ⭐️ 6.0/10

哈尔滨工业大学的研究团队提出了一种界面工程策略，成功构筑了全可拉伸湿气发电机。他们通过将溶胀于水-甘油二元溶剂中的高粘附性水凝胶集成在液态金属与可拉伸银电极之间，使器件在 85%相对湿度下获得了 0.94 V 的开路电压和 141 μA cm⁻²的电流密度，并能稳定输出超过 220 小时。 这项进展解决了可穿戴和植入式电子设备的一个关键瓶颈：需要能在动态环境中持续工作的耐用、可拉伸电源。通过解决界面粘附薄弱的问题，它为开发能够在折叠、拉伸等复杂形变下保持稳定能量收集的自供电可穿戴设备开辟了新路径。 增强的界面赋予了器件卓越的机械鲁棒性，在经历 8000 次折叠循环和 1000 次拉伸循环后性能衰减可忽略不计。水凝胶中的甘油不仅通过暴露更多氢键官能团增强了界面粘附，还赋予了器件抗干燥、抗冻及抗溶胀的性能。

rss · 科学网 - 精选博文 · 6月20日 06:05

**背景**: 湿气发电机是一种通过吸湿材料中带电离子的定向扩散，将环境湿气转化为电能的装置，有望提供连续的电源。然而，基于水凝胶的全可拉伸湿气发电机一直面临水凝胶与电极之间粘附力弱的关键问题，导致界面电阻高且在应变下易发生机械失效。界面工程是材料科学中的一种方法，专注于调控不同组件之间界面的性质，以提升整体器件性能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://academic.oup.com/nsr/article/12/11/nwaf171/8120212">Moisture-enabled electricity generation | National Science ...</a></li>
<li><a href="https://www.sciencedirect.com/science/article/pii/S2590123024003797">Interfacial Engineering for Advanced Functional Materials ...</a></li>

</ul>
</details>

**标签**: `#Energy Harvesting`, `#Materials Science`, `#Wearable Technology`, `#Nanotechnology`, `#Renewable Energy`

---

<a id="item-12"></a>
## [研究揭示 AI 可能导致技能退化，挪威出台教育限制政策](https://www.solidot.org/story?sid=84630) ⭐️ 6.0/10

一项针对波兰内窥镜医生的研究表明，在使用 AI 系统辅助诊断结肠腺瘤后，医生在没有 AI 辅助时的腺瘤检出率从 28.4%下降至 22.4%。此外，挪威政府宣布限制生成式 AI 在教育中的使用，6-13 岁小学生被禁止使用，14-16 岁学生需在教师指导下谨慎使用。 在医学等高风险专业领域出现技能退化的证据，对 AI 依赖如何影响人类长期专业能力和决策提出了严峻拷问。挪威的政策回应则反映了全球对 AI 可能干扰基础学习的日益增长的担忧，以及教育领域需要主动治理的迫切性。 技能退化效应是在 AI 工具不可用时被观察到的，这表明了依赖性问题。挪威的新政策将于 8 月下旬的新学年生效，该政策还包括为课堂提供更多书籍提供资金，以扭转平板电脑过度普及的趋势。

rss · 奇客Solidot–传递最新科技情报 · 6月20日 14:43

**背景**: 腺瘤是结肠中的癌前病变，在结肠镜检查中发现腺瘤对于预防结直肠癌至关重要。AI 辅助诊断工具旨在通过实时标记可疑区域来提高腺瘤检出率（ADR）。生成式 AI 工具，如大语言模型，可以生成文本、代码等内容，这引发了人们对其影响写作和批判性思维等核心技能学习的担忧。

<details><summary>参考链接</summary>
<ul>
<li><a href="http://www.bgjj.cc/fengshui/8606592.html">AI 让医生6个月“废功”20%，癌症 检 出率崩盘_家居风水_布谷家居网</a></li>
<li><a href="https://www.zgeo.com.cn/news/norway-bans-ai-for-elementary-school">挪威禁止小学生使用生成式AI | 智脑时代 ZGEO</a></li>

</ul>
</details>

**标签**: `#AI Ethics`, `#Skill Atrophy`, `#Education Policy`, `#Robotics`, `#Human-AI Interaction`

---

<a id="item-13"></a>
## [挪威将于 2026 年新学年起禁止小学生使用生成式 AI，并对中学生实施分级限制。](https://unwire.hk/2026/06/20/norway-ai-ban-elementary-school-2026/ai/?utm_source=rss&utm_medium=rss&utm_campaign=norway-ai-ban-elementary-school-2026) ⭐️ 6.0/10

挪威首相 Jonas Gahr Støre 于 6 月 19 日宣布，从 2026 年 8 月新学年起，国家将对小学生（6-13 岁）近乎全面禁止使用生成式 AI 工具。该政策同时对中学生实施分级限制，14-16 岁学生可在教师监督下谨慎使用，17-19 岁学生则应学习如何适当使用。 这是全球首批针对低龄学生、在教育领域实施的全面性生成式 AI 禁令之一，标志着政策从探索转向审慎监管的重大转变。它突显了全球范围内对 AI 可能损害学生基础学力、认知发展和学术诚信的日益增长的担忧。 此次 AI 禁令是挪威一系列更广泛教育政策的一部分，该系列政策还包括 2024 年的校园手机禁令和 2026 年资助纸质教科书的计划。实施 AI 禁令的主要原因是学生基础学力出现令人警惕的下滑，政策旨在保护核心学习过程。

rss · 香港 unwire.hk 玩生活．樂科技 · 6月20日 11:00

**背景**: 生成式 AI 指的是像 ChatGPT 和 Google Gemini 这样的人工智能系统，它们能够根据用户提示生成文本、代码或图像等新内容。自 2022 年底 ChatGPT 公开发布以来，其在教育领域的应用引发了全球性辩论，人们需要在将其作为学习工具的潜力与过度依赖、剽窃、阻碍批判性思维和写作技能发展等风险之间取得平衡。不同国家和机构正在探索多样化的监管路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.studioglobal.ai/zh-cn/discover/answers/searching-with-cited-sources-for-what-restrictions-6a35b8199529f7c3d45c0498">挪威小学几乎全面禁用AI：按年龄分级新规详解及背后考量</a></li>
<li><a href="https://abmedia.io/norway-near-ban-generative-ai-elementary-school-2026">挪威國小近全面禁 AI、6-13 歲適用、8 月新學年起 | 鏈新聞 ABMedia</a></li>

</ul>
</details>

**标签**: `#AI Regulation`, `#Education Technology`, `#Generative AI`, `#Policy`

---

<a id="item-14"></a>
## [读者与创作者日益重视 2022 年前的书籍与信息，因其感知可信度更高。](https://notes.lorenzogravina.com/musings/pre-2022-books) ⭐️ 5.0/10

一场社区讨论突显了一种日益增长的观点：与人工智能生成内容广泛传播后创建的内容相比，2022 年之前创作的书籍和在线信息被认为质量更高、更值得信赖。这种观点源于对亚马逊等平台充斥低质量 AI 生成参考书的观察，以及对较新在线信息可靠性的担忧。 这一趋势预示着数字信息生态系统可能面临信任危机，大量低质量 AI 内容正在贬低新信息来源的价值，并使知识发现过程复杂化。它影响着寻求可靠信息的读者、其真实作品可能被不公平忽视的 2022 年后作者与出版商，以及努力应对内容质量和真实性问题的平台。 讨论指出，许多有问题的 AI 生成内容是使用非前沿模型廉价创建的，缺乏事实核查、编辑或适当的排版。一个关键担忧是，即使是真正由人类撰写的 2022 年后内容，也可能被检测工具错误地标记为 AI 生成，这为创作者制造了一个悖论。

hackernews · trms · 6月20日 22:36 · [社区讨论](https://news.ycombinator.com/item?id=48613631)

**背景**: 2022 年 11 月 ChatGPT-3.5 的发布是一个转折点，导致了在线人工智能生成内容（AIGC）的爆炸式增长。Copyleaks 等机构的研究发现，从 2022 年 11 月到 2024 年 3 月，互联网上的 AI 内容激增了 8,362%。这种扩散涵盖了文本、图像和网站等多个领域，引发了人们对信息质量、准确性以及潜在错误信息的广泛担忧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.technewsworld.com/story/copyleaks-study-finds-explosive-growth-of-ai-content-on-the-web-179161.html">Copyleaks Study Finds Proliferation of AI Content on the Web</a></li>
<li><a href="https://arxiv.org/abs/2412.01948">[2412.01948] The Evolution and Future Perspectives of ... Copyleaks Study Finds Proliferation of AI Content on the Web The Evolution and Future Perspectives of Artificial ... One-Third of New Websites Are Now AI-Generated, Stanford ... A Survey of AI-Generated Content (AIGC) - ACM Digital Library</a></li>

</ul>
</details>

**社区讨论**: 评论者分享了有意识地寻找 2022 年前书籍以避免亚马逊上 AI 生成垃圾内容的经历，以及在查找技术信息时偏爱较旧在线帖子的做法。担忧包括 2022 年后人类作品的价值被贬低、通过回溯帖子日期进行 SEO 操纵的可能性，以及错误标记人类写作的 AI 检测工具的不可靠性。

**标签**: `#AI-generated-content`, `#information-quality`, `#community-discussion`, `#publishing`

---

<a id="item-15"></a>
## [《F-15 Strike Eagle II》DOS 游戏逆向工程寻求测试员，进行 DOS 到 C 语言的转换。](https://neuviemeporte.github.io/f15-se2/2026/06/20/needyou.html) ⭐️ 5.0/10

一个针对经典 DOS 游戏《F-15 Strike Eagle II》的逆向工程项目正在寻求测试员，以帮助验证一个已将原始汇编代码转换为功能等效的 C 代码的版本。该项目当前的目标是在将其移植到 Linux 和 Windows 等现代平台之前，确保基于 DOS 的 C 语言版本没有错误。 这项工作对于软件保存具有重要意义，因为它旨在创建一个可移植、可维护的 C 语言代码库，使其寿命超越原始的 DOS 平台和模拟器。它展示了一种从过时中拯救旧软件的系统性方法，可以应用于其他经典游戏。 该项目采用多步骤流程：首先将游戏完全逆向工程为汇编代码，然后在仍在 DOS 上运行的情况下，将该汇编代码转换为二进制等效的 C 代码。测试员需要原版游戏的 451.03 版本，并结合 DOSBox 或真实的 DOS 硬件，以帮助发现转换过程中引入的错误。

hackernews · LowLevelMahn · 6月20日 15:10 · [社区讨论](https://news.ycombinator.com/item?id=48609766)

**背景**: DOS 游戏通常使用汇编语言编写以获得高性能，这使得它们很难直接移植到现代系统。像 masm2c 这样的工具可以将 16 位 x86 汇编语言翻译成 C 语言，作为一种源到源的翻译器来促进移植。为保存而进行的逆向工程涉及分析和重建软件逻辑，以创建新的、可理解的源代码，这一过程通常使用 Ghidra 等框架。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/xor2003/masm2c">GitHub - xor2003/masm2c: x86 assembler (MASM syntax) to C ... c - How to convert a text file from DOS format to UNIX format ... dos2unix and unix2dos commands - GeeksforGeeks Celsius conversion calculators, tables and formulas (ºC) Dos to Unix Converter - Tool Slick</a></li>
<li><a href="https://www.apriorit.com/dev-blog/hardware-reverse-engineering">Hardware Reverse Engineering : Use Cases and Benefits - Apriorit</a></li>
<li><a href="https://maniacsvault.net/articles/dosporting">Porting Games from DOS to Modern Platforms - Blzut3's Weblog</a></li>

</ul>
</details>

**社区讨论**: 社区讨论显示出怀旧玩家和技术爱好者的兴趣。一个被提出的关键问题是逆向工程与使用 DOSBox 等模拟器相比的动机，项目负责人澄清其目标是为未来移植创建一个干净的 C 代码库。另一条评论则强调了现代游戏移植的简易性，与这种详细的汇编级工作形成对比。

**标签**: `#reverse-engineering`, `#game-development`, `#retro-computing`, `#software-preservation`

---

<a id="item-16"></a>
## [StartupWiki 作为 Crunchbase 的免费开源替代品发布。](https://startupwiki.tech/) ⭐️ 5.0/10

一位开发者推出了 StartupWiki，这是一个受维基百科模式启发的免费开源初创公司数据库项目。该项目处于早期阶段，目前提供初创公司档案、搜索、筛选、分类以及一个仍在开发中的公共 API。 这很重要，因为它挑战了像 Crunchbase 这样的商业数据库的订阅模式，旨在为研究人员、投资者和企业家提供更民主化的初创公司信息访问。如果成功，它可以为商业数据培育一个更开放、协作的生态系统，类似于维基百科对百科全书知识的影响。 该项目明确表示处于非常早期的阶段，社区评论强调了对其数据可靠性和验证的严重担忧，有用户指出其“已验证”徽章缺乏来源证明。开发者正在积极寻求关于所需信息、缺失功能以及 API 使用案例的反馈。

hackernews · shpran · 6月20日 15:59 · [社区讨论](https://news.ycombinator.com/item?id=48610224)

**背景**: Crunchbase 是领先的私人和上市公司信息数据库，其数据来源于人工智能、实时源和一个庞大的社区，但它采用基于订阅的商业模式。公共 API 提供了对数据的程序化访问，并且各个领域免费和开放的 API 生态系统正在不断增长。开源数据库项目，例如基于 PostgreSQL 构建的项目，为专有系统提供了社区驱动、透明的替代方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Crunchbase">Crunchbase - Wikipedia</a></li>
<li><a href="https://mixedanalytics.com/blog/list-actually-free-open-no-auth-needed-apis/">Big List of Free and Open Public APIs (No Auth Needed) GitHub - public-api-lists/public-api-lists: A curated list of ... GitHub - public-apis/public-apis: A collective list of free APIs Best Startup Data APIs for Developers (2026) | Netrows Blog Best Startup Revenue Data APIs for Developers (2026) A Collaborative List Of 1400+ Public APIs For Developers</a></li>
<li><a href="https://www.techtarget.com/searchdatamanagement/feature/Top-open-source-databases-to-consider">12 Top Open Source Databases to Consider - TechTarget</a></li>

</ul>
</details>

**社区讨论**: 讨论集中在实际挑战上：用户担心数据可靠性以及没有明确来源的“已验证”徽章的意义。建议包括从 Y Combinator 投资组合等已知来源抓取数据，并专注于构建强大的 API 和数据管道，而不是手动管理所有信息。

**标签**: `#startups`, `#open-data`, `#databases`, `#community-project`, `#api`

---

<a id="item-17"></a>
## [AICon 上海大会专题演讲：探讨大模型驱动的银行信贷全链路变革](https://www.infoq.cn/article/TbCYkGW0XrYuhSK1NE2p) ⭐️ 5.0/10

嘉银科技解决方案总监徐桢将于 6 月 26-27 日在 AICon 2026 上海站发表题为《AI 大模型驱动银行信贷业务的全链路变革》的主题演讲。该演讲将聚焦大模型在银行信贷四大核心场景的应用，包括解放客户经理重复性工作、推动风控智能化、精细化数据挖掘以及平衡客服成本与体验。 此次演讲的重要性在于，它探讨了 AI 从实验走向规模化、工程化生产的关键转变，尤其是在风险与合规要求极高的金融信贷领域。大模型的应用若能成功落地，将为银行带来显著的效率提升、更精准的风险识别和更低的运营成本，从而塑造数字信贷的未来。 演讲内容将包含国内外前沿实践的对比，并对技术融合、模式创新及合规升级等行业未来方向进行展望。主讲人徐桢拥有超过 20 年的信贷风险管理经验，曾任职于交通银行、浦发银行总行，并在同盾科技、度小满等金融科技公司担任要职。

rss · InfoQ 推荐 · 6月20日 02:00

**背景**: 以 DeepSeek 为代表的大模型正被工商银行、建设银行等超 20 家国内银行加速部署，推动金融服务从“信息化”迈向“认知化”。在信贷风控领域，行业正从依赖人工经验的简单规则筛查，转向构建多层次、智能化的风险分析引擎。所谓“智能体操作系统”(Agentic Operating System)，是一种上下文管理系统，它使 AI 智能体能够执行自主、协调的行动，而不仅仅是提供信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.21jingji.com/article/20250310/herald/2c9eb537431857e69d69ffc04e0a4335.html">国有 大 行 加速布局DeepSeek 推动金融服 务 从“信息化”迈向“ 认 知 化” - 21...</a></li>
<li><a href="https://tech.tom.com/202403/4083438229.html">纵横一体 化 服务 同盾助力某城商行构建全流程 智 能 信 贷 风 控 体系</a></li>
<li><a href="https://www.mindstudio.ai/blog/what-is-agentic-operating-system-9-components">What Is an Agentic Operating System ? 9 Components... | MindStudio</a></li>

</ul>
</details>

**标签**: `#AI-in-Finance`, `#Large-Language-Models`, `#Banking-Technology`, `#Conference`

---