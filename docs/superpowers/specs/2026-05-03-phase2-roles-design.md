# Phase 2 角色实现设计

## 概述

Phase 2 实现 5 个量化角色模板（06, 07, 09, 12, 13），延续 Phase 1 确立的模板模式。

## 设计原则（继承 Phase 1）

- Persona：深度模仿机构真实文化，第一人称专家口吻
- 任务维度：每个角色 5-7 个实质性维度，每个维度含公式/伪代码/Python 框架
- 占位符：全部保留 `{user_market}`, `{user_capital}`, `{user_focus}`, `{upstream_params}`, `{upstream_summary}`, `{project_architecture}`
- 质量门：末尾 `[QAGATE]...[/QAGATE]` 块，含 method_signature, data_signature, numerical_disclaimer
- 学术引用：≥5 篇关键论文/文献

## 角色清单

### 06 — AQR 因子模型构建师
- **机构文化**：学术严谨，Asness/Ilmanen 传统，因子即是信仰
- **depends_on**：02（回测结果）
- **核心维度**（6 个）：
  1. 因子定义与经济学逻辑（Value/Momentum/Carry/Quality/Low Vol/Size）
  2. 因子构建方法（多空组合、分位数分组、Fama-MacBeth 回归）
  3. 因子正交化与去冗余（Gram-Schmidt、PCA、最小角回归）
  4. 因子择时（估值扩散、动量择时、宏观状态择时）
  5. 因子组合（等权、波动率加权、最大化分散度）
  6. 因子衰退检测与生命周期管理
- **预估行数**：600-800

### 07 — D.E. Shaw 统计套利研究员
- **机构文化**：数学驱动、计算至上、极度谨慎
- **depends_on**：01（策略架构）
- **核心维度**（6 个）：
  1. 协整检验（Engle-Granger、Johansen、Phillips-Ouliaris）
  2. 配对交易（配对筛选、对冲比率估计、交易信号生成）
  3. 卡尔曼滤波动态对冲（状态空间模型、时变 β）
  4. 均值回归建模（Ornstein-Uhlenbeck 过程、半衰期估计）
  5. 统计篮子套利（PCA 残差、多资产协整）
  6. 交易成本与容量约束下的统计套利可行性
- **预估行数**：500-700

### 09 — Bloomberg 数据管道架构师
- **机构文化**：数据霸权、可靠性至上、标准化即信仰
- **depends_on**：-（独立角色）
- **核心维度**（6 个）：
  1. 数据源评估矩阵（可靠性、延迟、覆盖、成本）
  2. 实时数据管线（WebSocket/Redis Stream/Kafka）
  3. 历史数据管线（Parquet 分层存储、时间分区）
  4. 数据清洗 Pipeline（ETL 标准化、异常检测、缺失补全）
  5. Point-in-Time 数据版本管理
  6. 数据 API 设计（查询语言、权限、限流）
- **预估行数**：500-700

### 12 — Man Group 组合优化师
- **机构文化**：系统化、技术前沿、学术与实战并重
- **depends_on**：01, 02, 03, 06（策略、回测、风控、因子）
- **核心维度**（7 个）：
  1. 均值-方差优化（Markowitz、约束建模、求解器选择）
  2. 风险平价与风险预算（Spinu 算法、波动率分解）
  3. Black-Litterman 模型（先验均衡、观点融合、后验权重）
  4. 交易成本感知优化（市场冲击项、换手率惩罚）
  5. 鲁棒优化（不确定集、Worst-Case 方法）
  6. Walk-Forward 与 CPCV（Purged 交叉验证、样本外测试）
  7. 再平衡策略（日历再平衡、阈值触发、税收感知）
- **预估行数**：700-900

### 13 — Millennium 交易系统架构师
- **机构文化**：工程优先、低延迟、风险隔离、容灾至上
- **depends_on**：10, 12（执行算法、组合优化）
- **核心维度**（6 个）：
  1. 订单管理系统 OMS（订单生命周期、状态机、FIX 协议）
  2. 执行管理系统 EMS（智能路由、SOR 算法、暗池/显示池）
  3. 延迟优化（colocation、FPGA、内核旁路、锁竞争消除）
  4. 系统架构（微服务/单体、事件溯源、CQRS）
  5. 容灾与高可用（主备切换、脑裂防护、数据一致性）
  6. 监管合规嵌入（Pre-trade Risk Check、Position Limit、Reg SHO/MiFID II）
- **预估行数**：500-700

## 验收标准

- [ ] 5 个角色模板文件全部创建
- [ ] 每个文件含 ≥5 个实质性维度
- [ ] 每个文件含 `[QAGATE]` 质量门块
- [ ] 所有占位符完整保留
- [ ] SKILL.md 注册表无需修改（Phase 2 角色已在表中）
