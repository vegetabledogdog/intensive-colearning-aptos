---
timezone: Asia/Shanghai
---

# Nicole

1. 自我介绍
   * 大家好，我是Nicole，对于Defi感兴趣，希望可以get一些前沿技术在玩儿什么hh。
   
3. 你认为你会完成本次残酷学习吗？
   * 努力！

## Notes

<!-- Content_START -->

### 2024.09.07

1. 学习了残酷学习的学习、打卡方式和机制
2. 了解了aptos的基础知识
* 确认开发工具idea以及插件Move on Aptos
* 明确了学习资料的地址
  问题搜索地址：https://github.com/aptos-labs/aptos-developer-discussions/discussions
  
  交易查询地址：https://explorer.aptoslabs.com/?network=mainnet

### 2024.09.08

1. 学习配置开发环境
2. 浏览Aptos白皮书
    Aptos 区块链设计原则：扩展性、安全性、可靠性和可升级性。
  * 首先，Aptos 区块链原生集成并在内部使用 Move 语言进行快速和安全的交易执行。Move 验证器是一个用于用 Move 语言编写的智能合约的形式验证器，为合约不变量和行为提供额外的保障。这种对安全的关注使开发者能够更好地保护他们的软件免受恶意实体的攻击。
  * 其次，Aptos 数据模型支持灵活的密钥管理和混合托管选项。这与在签名前的交易透明度和实用的轻客户端协议一起，提供了更安全和更值得信赖的用户体验。
  * 第三，为了实现高吞吐量和低延迟，Aptos 区块链在交易处理的关键阶段采用流水线和模块化方法。具体来说，交易传播、块元数据排序、并行交易执行、批量存储和账本认证都同时进行。这种方法充分利用所有可用的物理资源，提高硬件效率，并实现高度并行执行。
  * 第四，与其他需要预先知道要读写的数据从而打破交易原子性的并行执行引擎不同，Aptos 区块链不会对开发者施加这样的限制。它可以有效地支持任意复杂交易的原子性，为实际应用提供更高的吞吐量和更低的延迟，并简化开发。
  * 第五，Aptos 模块化架构设计支持客户端的灵活性，并针对频繁和即时升级进行了优化。此外，为了快速部署新技术创新并支持新的 Web3 用例，Aptos 区块链提供了嵌入式链上变更管理协议。最后，Aptos 区块链正在试验未来的举措，以超越单个验证器的性能进行扩展：其模块化设计和并行执行引擎支持验证器的内部分片，同质状态分片为水平吞吐量可扩展性提供了潜力，而不会给节点运营商增加额外的复杂性。
   
### 2024.09.09

1. Aptos 节点是 Aptos 生态系统的一个实体，用于跟踪 Aptos 区块链的状态。客户端通过 Aptos 节点与区块链交互。有两种类型的节点：
* Validator nodes 验证节点
* Fullnodes 全节点
** 每个Aptos节点都包括几个逻辑组件
  REST API service
  Mempool
  Execution
  Virtual Machine
  Storage
  State synchronize 状态同步器
##### 讨论区资料补充：https://github.com/aptos-labs/aptos-developer-discussions/discussions

### 2024.09.10

1. 交易从构建到链上执行需要经历5个步骤：构建、模拟、签名、提交、等待。
2. 节点网络和同步：验证器节点和全节点形成层次结构，验证器节点位于根，全节点位于其他位置。验证器全节点直接连接到验证器节点，并提供可扩展性和 DDoS 缓解功能。公共全节点连接到验证器全节点（或其他公共全节点）以获得对 Aptos 网络的低延迟访问。
3. Move 是一种安全可靠的 Web3 编程语言，强调稀缺性和访问控制。 Move 中的任何资产都可以由 resources 表示或存储在resources中。默认情况下会强制实施稀缺性，因为结构不会被意外复制或删除。只有在字节码层明确定义为copy 的结构才可以分别被复制和drop 。
4. 交易和状态：
   * 交易：交易代表区块链上的账户执行的预期操作（例如，转移资产）。（只有交易才能改变账本状态）
   * 状态：（区块链账本）状态代表交易执行输出的累积，即存储在所有资源中的值。
   * 事件：执行交易时发布的辅助数据。


### 2024.09.11

### 2024.09.12
1. 区块：
   - Aptos 是一个按交易版本控制的数据库。执行交易时，每笔交易的结果状态都会单独存储，从而允许更精细的数据访问。这与其他区块链不同，其他区块链只存储区块（一组交易）的结果状态。
   - 区块仍然是 Aptos 的基本单位。交易被分批处理并在一个区块中一起执行。此外，存储中的证明处于区块级粒度。区块内的交易数量取决于网络活动和可配置的最大区块大小限制。
2. 质押：任何人都可以参与 Aptos 共识过程，只要他们质押了足够的实用币，即将他们的实用币存入托管账户。为了鼓励验证者参与共识过程，每个验证者的投票权重与验证者的质押金额成正比。作为交换，验证者将按质押金额的比例获得奖励。因此，区块链的性能与验证者的利益（即奖励）保持一致。
   - Owner
   - Operator
   - Voter
4. Aptos 主网纪元设置为 7200 秒（两小时）。
5. 奖励公式
```text
    Reward = staked_amount * rewards_rate per epoch * (Number of successful proposals by the validator / Total number of proposals made by the validator) 
```
### 2024.09.13
- 边学边忘🤦，简单复习了一下最初的直播内容
- 下周多抽时间来研究

### 2024.09.14

### 2024.09.15

### 2024.09.16

### 2024.09.17

### 2024.09.18

### 2024.09.19

### 2024.09.20

### 2024.09.21

<!-- Content_END -->
