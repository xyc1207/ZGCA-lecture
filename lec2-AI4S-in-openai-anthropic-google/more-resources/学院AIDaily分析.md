# OpenAI、Anthropic 与 Google 的 AI4Science 进展

**整理日期** 2026 年 11 月 6 日  
**日报范围** 2026 年 9 月 11 日至 11 月 5 日，共 56 期

按六类整理 AI Daily 中与三家公司相关的进展，重点条目附原始论文、系统卡或官方发布。日期采用原始发布日，少数早期项目用于交代技术路线。**★** 表示相对原 Word 调研补入的项目或证据。[AI Daily 归档](https://ai-daily.web.ihainan.me/index.html) · [原调研报告](https://chatgpt.com/library?file_id=libfile_2c0103bb18e08191a26a6e09969334e1&account_id=personal)

## 1. 科学模型

| 公司 | 代表进展 | 来源 |
|---|---|---|
| **OpenAI** | **GPT‑4b micro** 用蛋白序列、离散化三维结构和科学文本等数据训练，直接生成蛋白变体。与 Retro Biosciences 合作的实验中，细胞重编程标志物表达超过野生型对照 50 倍。**GPT‑Rosalind** 面向生命科学推理和工具使用。10 月 30 日系统卡显示，**Rosalind‑6 与 GPT‑6 Astra 共用权重，此次发布没有新增训练数据或额外后训练**。 | [Retro 合作成果](https://openai.com/index/accelerating-life-sciences-research-with-retro-biosciences/) · [Rosalind‑6 系统卡](https://deploymentsafety.openai.com/gpt-rosalind-6) |
| **Anthropic** | 在公开蛋白设计案例中，**Claude 调度专业模型**，选择设计位点，组合结构生成和序列设计模型，安排共折叠验证与筛选。实验结果评价的是整套设计流程。 | [蛋白设计研究](https://www.anthropic.com/research/Claude-accelerates-protein-design) |
| **Google / DeepMind** | **AlphaFold 3** 预测蛋白、核酸和小分子等复合体系的结构，**AlphaGenome** 从约 1 Mb DNA 预测功能组学信号。**★ AlphaProtein Novo** 给定催化基序与配体，用扩散模型联合生成蛋白结构与序列，再用 AF3 等工具筛选。预印本报告了哌啶合成和 DEHP 降解的酶活性结果，团队发布了设计代码。这是本次新增工作中与 NatureLM 的条件科学对象生成最直接相关的一项。 | [AlphaFold 3](https://blog.google/innovation-and-ai/products/google-deepmind-isomorphic-alphafold-3-ai-model/) · [AlphaGenome 论文](https://doi.org/10.1038/s41586-025-10014-0) · [AlphaProtein Novo 预印本](https://www.biorxiv.org/content/10.64898/2026.10.01.756017v1) · [设计代码](https://github.com/google-deepmind/alphaprotein-novo) |

## 2. Scientific Harness 与科研任务执行

- **OpenAI｜Rosalind Workbench 与并行分析。** Workbench 把科学工具、结构和序列查看器、分析记录放进同一工作环境。10 月 21 日，OpenAI、PerturbAI 和 Scripps 用数千个 Rosalind agent 分析已有的小鼠全脑扰动数据，**32 分钟完成分析**。盲评中，专家在 75% 的比较中偏好分布式报告，团队据此提出了可继续验证的机制假说。[Workbench](https://developers.openai.com/blog/rosalind-workbench) · [全脑数据分析](https://openai.com/index/scaling-ai-research-for-complex-biological-data/)
- **Anthropic｜Claude Science 与可审查的分析产物。** 工作台接入 Python/R、科学数据库和本地或远程算力，把代码、数据和结果关联起来。在 vault 项目中，内部多智能体系统在研究人员指导下配置并运行 RELION，**34 小时得到初版结构模型**，最终图谱约一周完成。[Claude Science](https://www.anthropic.com/news/claude-science-ai-workbench) · [Vault 研究](https://www.anthropic.com/research/investigating-vault-particles-with-claude)
- **Google｜Co‑Scientist 与 Antigravity。** Co‑Scientist 用多个智能体生成、批评、排序和修订假设，已有白血病药物再利用、肝纤维化等验证案例。11 月 3 日发布的 **Cheminformatics Skills** 演示用 Gemini 规划，调用 ChEMBL、PubChem 和 RDKit 完成检索、匹配分子对分析和大环候选设计，约一小时交付计算方案。**ProtNLM + Antigravity** 从未注释蛋白中寻找抗菌肽，候选处于湿实验验证阶段。**★** 同日，Google 宣布 Computational Discovery 可通过 MCP 接入兼容的 agent。[Co‑Scientist](https://deepmind.google/blog/co-scientist-a-multi-agent-ai-partner-to-accelerate-research/) · [化学信息学演示](https://deepmind.google/blog/agentic-cheminformatics-with-google-antigravity/) · [抗菌肽发现](https://deepmind.google/blog/accelerating-antimicrobial-discovery/) · [Computational Discovery](https://research.google/blog/empirical-research-assistance-era-from-nature-publication-to-catalyzing-computational-discovery/)

## 3. 实验成果与验证终点

| 项目 | 已完成的验证 | 来源 |
|---|---|---|
| **OpenAI × Ginkgo｜无细胞蛋白合成** | GPT‑5 提议实验，云实验室执行并返回测量，反馈用于后续轮次。六轮研究在特定 sfGFP 体系中把每克蛋白的生产成本降低约 **40%**，形成了实验反馈闭环。 | [发布说明](https://openai.com/index/gpt-5-lowers-protein-synthesis-cost/) · [技术报告](https://cdn.openai.com/pdf/5a12a3bc-96b7-4e07-9386-db6ee5bb2ed9/using-a-gpt-5-driven-autonomous-lab-to-optimize-the-cost-and-titer-of-cell-free-protein-synthesis.pdf) |
| **OpenAI × Molecule.one｜化学反应优化** | GPT‑5.4 和 Maria 配合高通量实验室筛选反应条件。两轮共 **10,080 次反应**，所研究偶联反应的估计平均产率从 **16.6% 升至 25.2%**。 | [技术报告](https://cdn.openai.com/pdf/4934b0ed-3de2-4ac5-835c-97604d52dea7/tempo-improves-generality-and-decreases-oxidative-deboronation.pdf) |
| **Anthropic｜蛋白结合物设计** | 8 月项目在 **15 个靶点中的 14 个**获得结合物，1,320 个设计中有 354 个命中。**★ 10 月 20 日蝎毒项目**测试 211 个设计，17 个达到结合标准，测量终点为结合。团队公开了全部候选、预测结构、评分和实验数据。 | [8 月研究](https://www.anthropic.com/research/Claude-accelerates-protein-design) · [10 月研究](https://www.anthropic.com/research/claude-scorpion-toxin-binder-design) · [公开数据](https://huggingface.co/datasets/Anthropic/scorpion-toxin-binder-design) |
| **Anthropic｜自建实验室的基础生物学** | 9 月公布 ART 酶系统研究。11 月 4 日报告用冷冻电镜解析了在细菌表达体系中组装的噬菌体 L05 vault，颗粒由 **96 个蛋白拷贝**组成。Claude 参与数据库检索、分离方案和电镜数据处理。颗粒功能仍在研究中。 | [ART 酶系统](https://www.anthropic.com/research/claude-discovers-novel-enzyme-system) · [Vault 研究](https://www.anthropic.com/research/investigating-vault-particles-with-claude) |
| **★ Google｜Gemini 4 Argon 参与酶工程** | Argon 整理数据、微调蛋白模型并筛选候选，计算设计在数小时内完成。Google 报告后续实验中 **5 个设计均显示催化活性**。该案例展示了通用 agent 如何组织一个具体的模型适配与实验任务。 | [Argon 发布与酶工程案例](https://blog.google/intl/en-mena/product-updates/explore-get-answers/gemini-4-argon-built-to-solve-your-hardest-problems/) |
| **Anthropic × Janelia｜实验设备接口** | **Model Hardware Standard** 在研究预览中把设备状态、操作和约束交给 agent。Genentech 用它协调移液设备、机械臂和读板仪，完成 BCA 蛋白定量概念验证。 | [研究预览](https://www.anthropic.com/news/model-hardware-standard-research-preview) |

## 4. 数学、物理与 AI4AI

- **★ OpenAI｜数学发布与学术复核。** 9 月公布带光滑外力条件下 Navier–Stokes 有限时间奇性的证明稿和 Lean 形式化，Clay 页面仍标为 **Active**。10 月 26 日公布局部光滑与 Kakeya、指数时间假设 ETH、量子 Yang–Mills 理论存在性三项结果。三项采用不同的发布和复核方式，其中 Yang–Mills 稿件交由 David Gross 等人组成的委员会评估。[Navier–Stokes 公告](https://openai.com/index/navier-stokes-solution/) · [Clay 项目状态](https://www.claymath.org/millennium/navier-stokes-equation/) · [三项数学结果](https://openai.com/index/building-scientific-understanding-with-academic-communities/) · [Yang–Mills 工作组](https://www.kitp.ucsb.edu/sites/default/files/YM_working_group.pdf)
- **★ Google｜形式化证明与程序搜索。** **AlphaProof Nexus** 已发表于《Science》。系统生成 Lean 证明并用编译反馈继续搜索，报告解决 **9/353** 个开放 Erdős 问题和 **44/492** 个 OEIS 猜想。**AlphaEvolve / ERA** 由模型生成或改写程序，再运行程序评估候选，应用包括测序纠错、量子电路和单细胞分析方法。[Science 论文记录](https://pubmed.ncbi.nlm.nih.gov/42848891/) · [AlphaProof Nexus 预印本](https://arxiv.org/abs/2605.22763) · [AlphaEvolve 应用](https://deepmind.google/blog/alphaevolve-impact/) · [ERA 论文](https://doi.org/10.1038/s41586-026-10658-6)
- **Anthropic｜科研代码与量子电路优化。** 9 月用 Claude 优化了 **30 多个生物模型的推理实现**。允许极小精度变化时平均约快 4 倍，输出完全一致时接近 2 倍。**★ 10 月与哈佛等合作的量子电路预印本**用独立评估器验证候选，在 8 项任务中的 7 项同时减少 Toffoli 门和量子比特数。Anthropic 内部模型也同期提交了独立的 ETH 反驳稿。[生物模型优化](https://www.anthropic.com/research/claude-uplifts-biomolecular-modeling) · [量子电路预印本](https://arxiv.org/abs/2610.22367) · [ETH 稿件](https://hexagonmath.org/2610.00577v1)

## 5. 数据、评测与 Agentic Post‑Training

| 方向 | 代表进展 | 来源 |
|---|---|---|
| **可核验科研任务** | OpenAI 的 **FrontierScience** 公开 100 道竞赛题和 60 道带评分标准的研究子任务。Anthropic 的 **BioMysteryBench** 用 99 个基于真实数据、答案可核验的生信问题评估工具使用。**★ Agent4Sci** 要求 agent 改进 11 个领域的 20 个已发表科学 ML 基准。加入研究 skill 后，Claude Opus 在该设置中的平均相对改进从 **10.4% 升至 20.1%**，论文指出主要收益来自 ML 工程改进。 | [FrontierScience](https://openai.com/index/frontierscience/) · [BioMysteryBench](https://www.anthropic.com/research/Evaluating-Claude-For-Bioinformatics-With-BioMysteryBench) · [Agent4Sci](https://arxiv.org/abs/2610.28763) |
| **科学数据资产** | Google 的 **AlphaGenome Atlas** 将约 **90 亿种单碱基替换的预测效应**做成可查询资源。**★ 10 月的 Virtual Biology Initiative** 面向新的多模态测量和开放数据。Biohub 公布的 18 亿美元是多方资金、数据、计算和测量技术的合计承诺，DeepMind、Isomorphic Labs 与 Meta 共同承诺其中 3 亿美元。 | [AlphaGenome Atlas](https://deepmind.google/blog/alphagenome-atlas-a-predictive-map-of-every-possible-dna-letter-change-in-the-human-genome/) · [Biohub 合作公告](https://biohub.org/news/virtual-biology-initiative-expansion/) |
| **反馈用于更新什么** | **★ Google Harness²** 从任务执行和修改记录中提取经验，改进后续任务的 **harness 配置**。Argon 酶设计更新的是**被调用的蛋白模型参数**。Anthropic 披露 vault 项目的失败记录反馈给了 Claude 训练团队，影响其**训练数据选择**。 | [Harness²](https://arxiv.org/abs/2610.14224) · [Argon 酶设计](https://blog.google/intl/en-mena/product-updates/explore-get-answers/gemini-4-argon-built-to-solve-your-hardest-problems/) · [Vault 项目](https://www.anthropic.com/research/investigating-vault-particles-with-claude) |

## 6. 组织、合作与转化

| 公司 | 近期布局 | 来源 |
|---|---|---|
| **OpenAI** | 10 月推出 Rosalind Academic Plan。**★ 10 月 20 日宣布收购 Orchestra Bio**，计划把药物研发的研究进度、外部合作和决策管理接入 Rosalind。11 月 3 日公布 Codex 在 CAD、PCB、仿真和实体原型中的应用。 | [Academic Plan](https://openai.com/index/introducing-the-rosalind-academic-plan/) · [Orchestra Bio 公告](https://openai.com/index/openai-to-acquire-orchestra-bio/) · [工程应用](https://openai.com/index/accelerating-engineering-for-the-physical-world/) |
| **Anthropic** | 自建实验室开展基础生物学研究，与 Generate、BigHat、Enveda 等六家机构推进药物研发，覆盖设计、实验、制造文件和临床试验规划。10 月披露收购 **Mithril Medicine**，其项目已有早期小鼠结果。**★ 10 月 28 日**公布 AI for Science 扩展至 20 家基金会和研究机构。 | [药物研发合作与 Mithril](https://www.anthropic.com/research/early-progress-drug-development) · [科研机构合作](https://www.anthropic.com/news/ai-for-science-expands-foundations-research-institutions) |
| **Google / Alphabet** | DeepMind 开发科学模型与发现系统，Google Research 和 Cloud 提供计算、数据与部署入口。Alphabet 生态内独立的 **Isomorphic Labs** 用 IsoDDE 把结构、口袋与亲和力预测接入药物设计。生命科学之外，WeatherNext 3 已接入 Google 产品并逐小时更新，**★ ForTy** 在 10 月发布 10 米尺度的全球森林类型地图。 | [IsoDDE](https://www.isomorphiclabs.com/articles/the-isomorphic-labs-drug-design-engine-unlocks-a-new-frontier) · [WeatherNext 3](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/introducing-weathernext-3/) · [ForTy](https://deepmind.google/blog/beyond-tree-cover-mapping-the-worlds-forest-types/) |
