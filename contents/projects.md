---
sort: 1
---

# Projects

---



```note
## 分布式数据库与分布式系统一致性理论

数据库的ACID包括了一些传统的事务理论，包括事务的隔离级别、可恢复行等。但我们发现在分布式场景下，很多概念变得更加复杂难懂，有些问题用传统的理论解释乏力或者难以有效解释。究其原因，是数据分片、多版本等技术的引入使得之前的理论体系更加涣散。典型的例子如： 分布式数据库中快照隔离到底和分布式系统中的一致性有何关系，和数据库中的隔离级别又有何关系？分布式系统中研究的如SNOW理论和数据库中的一致性是和关系？Spanner在最高的一致性上作出了标准（可线性化+可串行化），但这仅是冰山一角，冰山下绝大多数实际系统中使用的一致性标准要低很多，而这方面的理论支持比较薄弱。项目意图是在数据库+分布式系统的一致性给出结合的理论框架，方便在系统设计时更容易的定位与思考问题。 
```



```note
## 基于持久化内存/SSD/云存储的OLAP混合存储引擎

OLAP的存储引擎面临两方面的需求，热数据查询性能更高，冷数据成本更低。因此，项目基于clickhouse的存储引擎搭建一个混合的存储引擎，该存储引擎包括三个部分：持久化内存层、SSD\磁盘存储层、云存储。 SSD\磁盘存储为原clickhouse的存储层。 项目使用持久化内存构建一个更快的OLAP存储引擎。在合理的使用下，持久化内存比SSD具有更好的读写性能，另外具有快速更新的能力，使得clickhouse在面临快速更新时的查询性能得到大幅提升。成本方面，云存储廉价的方式对OLAP的冷数据存储成本更低，另外通过优化clickhouse在云存储（OSS）的存储，比简单的适配OSS具有更高的查询性能。
```



```note
## 基于DRAM/持久化内存/SSD的LSM-tree架构的数据库存储
主要探索持久化内存在LSM-tree存储中的应用。LSM-tree的多个组成部分，内存表、日志、L0 SStable和下层的SStable以及缓存，都存在利用持久化内存的可能性。如何高效地利用持久化内存提升存储性价比是重要的研究课题。
```

```note
## 基于RDMA的数据库可计算查询共享缓存
```

```note
## 基于RDMA的数据库日志持久化与备份
```




```note
## DaseDB：基于PM和RDMA设计的新型分布式数据库系统
我们基于持久化内存和远程内存防伪(RDMA)这两种新型的存储与网络设备，设计了新型的分布式数据库架构。
```




# Previous Projects


```note
## Cedar：基于分布式LSM-tree架构的OLTP系统
华东师范大学数据学院数据库团队开发的可扩展分布式数据库， 详见[Cedar](https://github.com/daseECNU/Cedar)。
```




