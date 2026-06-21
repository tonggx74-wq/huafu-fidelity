# 华服保真 · HuaFu-Fidelity

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20780674.svg)](https://doi.org/10.5281/zenodo.20780674)

**面向国际传播的中华服饰视觉形象文化失真识别系统（可解释界面 · 研究雏形）**
*An explainable-interface prototype for recognizing cultural distortion of Chinese costume (Hanfu, Qipao, ethnic dress) in generative-AI content for international communication.*

> ⚠️ **这是一个开源研究雏形，不是训练好的模型。** 识别由**透明、可审计的专家规则知识库**驱动（见 `index.html` 中的 `KB` 对象）。在完整系统中，“算法初筛”将由机器学习承担；本雏形以规则库保证**可复现、可解释**，用于演示识别机制、可解释界面与人机协同流程。
>
> **This is an open-source research prototype, not a trained model.** Recognition is driven by a transparent, auditable expert rule base (see the `KB` object in `index.html`). In the full system the “algorithmic pre-screening” stage would use machine learning; here a rule base keeps the demo reproducible and explainable.

---

## 这是什么 / What it is

本项目是课题《文明互鉴视域下中华服饰视觉形象的文化失真识别与设计干预研究》的**前期研究基础与开源原型**。它以**价值敏感设计（Value Sensitive Design）**为框架，把“文化保真”确立为可被识别与干预的核心设计价值，并把它逐层转译为可检核的设计指标：

```
价值 Value      文化保真 cultural fidelity
   ↓
规范 Norms      形制合朝代规制 · 纹样语义正确 · 工艺如实 · 礼制得体 · 文明不混并
   ↓
指标 Indicators 5 类失真 × 3 级程度的规则（KB.rules）
```

界面遵循 **透明 / 可解释 / 可审计** 原则，围绕三个可解释模块与一条人机协同流程展开。

## 功能 / Features

- **① 风险提示 Risk warning** — 可视化呈现失真**类型**与**等级**；对**跨文明归并、地域替代**等国际传播高发风险予以显性标识；提示强度按其对创作的**强制/说服**程度分层（强/中/弱提示），实现“信任校准”。
- **② 出处解释 Provenance** — 以**中外双语**显化服饰语义与文化规约，面向缺乏“对等物”的海外受众；预留**图文＋视听**多模态扩展位。
- **③ 对比显示 Comparison** — 将**中华服饰 vs 和服 vs 韩服**在领襟、腰系、廓形、纹样、穿法等区辨轴上并置，凸显关键差异。
- **④ 人机协同复核 Human-AI review** — 三阶流程：**算法初筛 → 设计师/文化专家复核（逐项确认/驳回/批注）→ 双语判定与出处标注**。
- **可审计 Auditable** — 每次识别与复核均带时间戳记录，可**导出双语判定标注（JSON）**与**审计日志（JSON）**，为内容出海生成可追溯标注。

涵盖的五类失真 / Five distortion types: 形制错置、纹样混淆、工艺误读、礼制偏移、**跨文明归并**（含地域替代）。

## 本地运行 / Run locally

无需安装、无依赖、无构建。No install, no dependencies, no build.

```bash
# 方式一：直接双击 index.html 用浏览器打开
# Option A: just open index.html in a browser

# 方式二：本地起一个静态服务器（推荐，字体加载更稳）
# Option B: serve it (recommended, so web fonts load)
python3 -m http.server 8000
# 然后访问 / then open  http://localhost:8000
```

## 在线演示 / Live demo

**▶ https://tonggx74-wq.github.io/huafu-fidelity/**

打开后，从左侧选择预设案例，或自定义服饰特征后点击“运行识别”。
Open the link, then pick a preset case on the left, or set features and click Run.

## 扩充知识库 / Extending the rule base

规则与释义集中在 `index.html` 的 `KB` 对象中，结构清晰，便于增补：
The rules and bilingual explanations live in the `KB` object in `index.html`:

```js
KB.rules         // 失真识别规则（type / severity / strength / when / zh / en / ref）
KB.conventions   // 出处解释卡片（双语 + 依据）
KB.comparison    // 中华 vs 和服 vs 韩服 区辨矩阵
PRESETS          // 预设演示案例
```

欢迎以 Pull Request 增补规则、纠正释义或补充权威依据。
Contributions (rules, corrections, references) via Pull Request are welcome.

## 引用 / Citation

本软件已在 Zenodo 永久存档，引用请用以下格式：
This software is archived on Zenodo. Please cite it as:

> 孟小愉. (2026). *HuaFu-Fidelity 华服保真：面向国际传播的中华服饰视觉形象文化失真识别系统（可解释界面雏形）* (Version 0.1.0) [Software]. Zenodo. https://doi.org/10.5281/zenodo.20780674

机器可读的引用信息见 [`CITATION.cff`](./CITATION.cff)。
Machine-readable citation metadata is in [`CITATION.cff`](./CITATION.cff).

## 学术依据 / Scholarly basis

规则与释义依据沈从文《中国古代服饰研究》、周锡保《中国历代服饰史》、黄能馥等《中华历代服饰艺术》及《论语》《新唐书·车服志》《明史·舆服志》等通行文献整理，仅供研究演示。
The rule base draws on standard references in Chinese costume history; it is for research demonstration only.

## 许可 / License

[MIT](./LICENSE)
