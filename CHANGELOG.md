# TiSpark Changelog
All notable changes to this project will be documented in this file.

## [TiSpark 2.5.0] 2022-01-25
### New feature
- Support Spark 3.1.x and 3.0.x version.
- Support Spark SQL's authentication and authorization through TiDB [#2185](https://github.com/pingcap/tispark/pull/2185).

### Fixes
- Fix duplicate range in RowIDAllocator [#2156](https://github.com/pingcap/tispark/pull/2156).
- upgrade log4j to 2.17.1 [#2197](https://github.com/pingcap/tispark/pull/2197).
- upgrade jackson-databind to 2.9.10.8 [#2161](https://github.com/pingcap/tispark/pull/2197).

### Documents
- Fix in user docs forget to use options while using BatchWrite [#2169](https://github.com/pingcap/tispark/pull/2169)

### Known issue
- Spark SQL's authentication and authorization through TiDB will affect other datasource such as hive. See details in this issue [#2224](https://github.com/pingcap/tispark/issues/2224).
- Batch write needs more tests and may be unstable. See details in this issue [#2222](https://github.com/pingcap/tispark/issues/2222).

## [TiSpark 2.4.3] 2022-01-25
### New feature
-  scala 2.11 and 2.12 are both supported

### Fixes
- Fix duplicate range in RowIDAllocator [#2208](https://github.com/pingcap/tispark/pull/2208).
- upgrade log4j to 2.17.1 [#2209](https://github.com/pingcap/tispark/pull/2209).
- upgrade jackson-databind to 2.9.10.8 [#2209](https://github.com/pingcap/tispark/pull/2209).

### Documents
- Fix in user docs forget to use options while using BatchWrite [#2171](https://github.com/pingcap/tispark/pull/2171).

### Known issue
- Batch write needs more tests and may be unstable. See details in this issue [#2222](https://github.com/pingcap/tispark/issues/2222).

## [TiSpark 2.4.2] 2021-11-02
Since TiSpark v2.4.2, Only Scala v2.12 is supported.
### New feature
- BatchWrite: support clustered index [(#2060)](https://github.com/pingcap/tispark/pull/2060) by @marsishandsome in [#2079](https://github.com/pingcap/tispark/pull/2079).
- Update to support scala-2.12 by @birdstorm in [#2149](https://github.com/pingcap/tispark/pull/2149).
- Update spark version info for v2.4 by @birdstorm in [#2155](https://github.com/pingcap/tispark/pull/2155).

### Fixes
- Fix region manager race [(#1987)](https://github.com/pingcap/tispark/pull/1987) by @ti-srebot in [#2092](https://github.com/pingcap/tispark/pull/2092).
- Fix ResolveLock not called in Scan API [(#2089)](https://github.com/pingcap/tispark/pull/2089) by @ti-srebot in [#2091](https://github.com/pingcap/tispark/pull/2091). 
- Fix region split: region split key should be a valid key by @marsishandsome in [#2101](https://github.com/pingcap/tispark/pull/2101).
- Optimize region cache miss [(#2106)](https://github.com/pingcap/tispark/pull/2106) by @ti-srebot in [#2107](https://github.com/pingcap/tispark/pull/2107).
- Fix catalog test [(#2110)](https://github.com/pingcap/tispark/pull/2110) by @ti-srebot in [#2113](https://github.com/pingcap/tispark/pull/2113).
- Fix channel shut-downed due to ping failure [(#2120)](https://github.com/pingcap/tispark/pull/2120) by @ti-srebot in [#2122](https://github.com/pingcap/tispark/pull/2122).
- Close TTLManager before creating a new one [(#2114)](https://github.com/pingcap/tispark/pull/2114) by @ti-srebot in [#2118](https://github.com/pingcap/tispark/pull/2118).
- Close PDClient without closing channel factory [(#2123)](https://github.com/pingcap/tispark/pull/2123) by @ti-srebot in [#2125](https://github.com/pingcap/tispark/pull/2125).
- Fix DateTime shift before the year 1582 [(#2104)](https://github.com/pingcap/tispark/pull/2104) by @birdstorm in [#2116](https://github.com/pingcap/tispark/pull/2116).
- Fix enum with trailing spaces [(#2127)](https://github.com/pingcap/tispark/pull/2127)  by @ti-srebot in [#2134](https://github.com/pingcap/tispark/pull/2134).
- Fix not leader error due to region not invalidated [(#2135)](https://github.com/pingcap/tispark/pull/2135)  by @ti-srebot in [#2138](https://github.com/pingcap/tispark/pull/2138).
- Fix BatchGet StackOverFlow Error [(#2126)](https://github.com/pingcap/tispark/pull/2126)  by @ti-srebot in [#2140](https://github.com/pingcap/tispark/pull/2140).

## [TiSpark 2.3.16] 2021-05-17
### Fixes
- Change PARTITION_PER_SPLIT default value from 1 to 10 [#2029](https://github.com/pingcap/tispark/pull/2029)
- Fix array index out of bound when encoding [#2041](https://github.com/pingcap/tispark/pull/2041)
- fix batch write missing unpersist [#2046](https://github.com/pingcap/tispark/pull/2046)
- Fix bug: write decimal(16, 4) using batch write and read using tiflash [#2055](https://github.com/pingcap/tispark/pull/2055)
- Fix mistake setting current_ts to 0 [#2067](https://github.com/pingcap/tispark/pull/2067)
- Filter views in catalog [#2071](https://github.com/pingcap/tispark/pull/2071)
- BatchWrite: add argument deduplicate [#2073](https://github.com/pingcap/tispark/pull/2073)

## [TiSpark 2.4.1] 2021-05-17
### Fixes
- Fix bug: write decimal(16, 4) using batch write and read using tiflash [#2055](https://github.com/pingcap/tispark/pull/2055)
- Fix mistake setting current_ts to 0 [#2067](https://github.com/pingcap/tispark/pull/2067)
- Filter views in catalog [#2071](https://github.com/pingcap/tispark/pull/2071)
- BatchWrite: add argument deduplicate [#2073](https://github.com/pingcap/tispark/pull/2073)

## [TiSpark 2.4.0] 2021-04-15
### New Features
- Support TiDB-5.0

## [TiSpark 2.3.14] 2021-04-12
### Fixes
- Fix GregorianCalendar [#1952](https://github.com/pingcap/tispark/pull/1952)
- Fix tiflash timestamp pushdown bug [#1966](https://github.com/pingcap/tispark/pull/1966)
- Do not select tidb_row_format_version if tidb is 3.x [#1993](https://github.com/pingcap/tispark/pull/1993)
- Update table statistics after batch write [#2009](https://github.com/pingcap/tispark/pull/2009)
- Fix oom cause missing data bug [#2010](https://github.com/pingcap/tispark/pull/2010)

## [TiSpark 2.3.13] 2021-03-05
### Fixes
- Disable index scan on partition table [#1923](https://github.com/pingcap/tispark/pull/1923)
- Fix jackson-databind [#1910](https://github.com/pingcap/tispark/pull/1910)
- Fix BatchGet retry [#1907](https://github.com/pingcap/tispark/pull/1907)

## [TiSpark 2.3.12] 2021-02-01
### Fixes
- Add retry in `RangeSplitter` [#1886](https://github.com/pingcap/tispark/pull/1886)
- Fix `TiDAGRequest` concurrent visit [#1893](https://github.com/pingcap/tispark/pull/1893)
- Fix partition table with partition column name `date` [#1892](https://github.com/pingcap/tispark/pull/1892)

## [TiSpark 2.3.11] 2020-12-17
### Fixes
- Fix the resolved txn status cache for pessimistic txn [#1868](https://github.com/pingcap/tispark/pull/1868)
- Fix overflow when convert big MyDecimal to BigDecimal [#1869](https://github.com/pingcap/tispark/pull/1869)
- Add retry in RowIDAllocator [#1856](https://github.com/pingcap/tispark/pull/1856)
- Fix select count where values contains null [#1841](https://github.com/pingcap/tispark/pull/1841)
- Do not retry for some key error [#1799](https://github.com/pingcap/tispark/pull/1799)
- Disable year type index scan [#1790](https://github.com/pingcap/tispark/pull/1790)

### New Features
- Support auto_random column [#1838](https://github.com/pingcap/tispark/pull/1838)
- Support log desensitization [#1805](https://github.com/pingcap/tispark/pull/1805)
- Support insert null on auto increment column [#1786](https://github.com/pingcap/tispark/pull/1786)

## [TiSpark 2.3.10] 2020-11-06
### Fixes
- Fix maven-shade-plugin relocation cannot handle folder name with dot [#1737](https://github.com/pingcap/tispark/pull/1737)
- BatchWrite: add parameter maxRegionSplitNum [#1729](https://github.com/pingcap/tispark/pull/1729)
- Fix string insert overflow check [#1727](https://github.com/pingcap/tispark/pull/1727)

## [TiSpark 2.3.9] 2020-10-31
### Fixes
- Revert "fix TiSession Close bug" [#1713](https://github.com/pingcap/tispark/pull/1713)
- Fix typo in DateTime calculation [#1710](https://github.com/pingcap/tispark/pull/1710)

## [TiSpark 2.3.8] 2020-10-30
### Fixes
- Fix negative column id when there are more than 128 columns [#1673](https://github.com/pingcap/tispark/pull/1673)
- Fix incorrect date type value when timezone is set [#1704](https://github.com/pingcap/tispark/pull/1704)
- BatchWrite: fix auto increment column not primary key [#1694](https://github.com/pingcap/tispark/pull/1694)
- Fix TiSession Close bug [#1677](https://github.com/pingcap/tispark/pull/1677)
- Optimize region split number in small data size [#1681](https://github.com/pingcap/tispark/pull/1681)

## [TiSpark 2.3.7] 2020-10-27
### Fixes
- BatchWrite: enable user provided auto increment value in update mode [#1658](https://github.com/pingcap/tispark/pull/1658)
- BatchWrite: fix initial ttl expired [#1660](https://github.com/pingcap/tispark/pull/1660)
- BatchWrite: fix commit ts expired [#1661](https://github.com/pingcap/tispark/pull/1661)

## [TiSpark 2.3.6] 2020-10-16
### Fixes
- Fix covering index error when alter-primary-key is enabled [#1640](https://github.com/pingcap/tispark/pull/1640)
- Fix alter primary key for write [#1644](https://github.com/pingcap/tispark/pull/1644)

## [TiSpark 2.3.5] 2020-09-25
### Fixes
- Fix scala match error when predicate includes boolean type conversion [#1620](https://github.com/pingcap/tispark/pull/1620)
- Fix encoder v2 with type conversion and set default batch write version to v2 [#1623](https://github.com/pingcap/tispark/pull/1623)
- Filter sequence table from catalog  [#1627](https://github.com/pingcap/tispark/pull/1627)
- Fix batch write failed because of MetaCodec.hashGet failed [#1636](https://github.com/pingcap/tispark/pull/1636)

## [TiSpark 2.3.4] 2020-09-15
### Fixes
- Filter Tombstone store [#1582](https://github.com/pingcap/tispark/pull/1595)
- Increase gRPC response default limit size to 2G [#1597](https://github.com/pingcap/tispark/pull/1597)
- Update txnPrewriteBatchSize & txnCommitBatchSize default value to 16K [#1599](https://github.com/pingcap/tispark/pull/1599)
- Update writeThreadPerTask default value to 2 [#1600](https://github.com/pingcap/tispark/pull/1600)
- Fix multiple database scan test bug [#1603](https://github.com/pingcap/tispark/pull/1603)
- Update grpc version to 1.29.0 [#1609](https://github.com/pingcap/tispark/pull/1609)
- BatchWrite: add parameter maxWriteTaskNumber [#1616](https://github.com/pingcap/tispark/pull/1616)

## [TiSpark 2.3.3] 2020-09-02
### Fixes
- Optimize scatter region logic [#1582](https://github.com/pingcap/tispark/pull/1582)
- Set regionSplitUsingSize default value to true [#1584](https://github.com/pingcap/tispark/pull/1584)
- User provided auto increment value is not supported [#1586](https://github.com/pingcap/tispark/pull/1586)
- Fix partition table on tiflash [#1588](https://github.com/pingcap/tispark/pull/1588)
- Use ShardRowIDBits to generate row id [#1585](https://github.com/pingcap/tispark/pull/1585)

## [TiSpark 2.3.2] 2020-08-21
### Fixes
- Fix batch write bug and optimize batch write execution [#1562](https://github.com/pingcap/tispark/pull/1562)
- Fix columnar batch execution [#1566](https://github.com/pingcap/tispark/pull/1566)
- Fix covering index generates incorrect plan when first column is not included in index [#1573](https://github.com/pingcap/tispark/pull/1573)
- Fix pytispark [#1557](https://github.com/pingcap/tispark/pull/1557)

## [TiSpark 2.3.1] 2020-07-08
### Fixes
- Ignore get version sql exception [#1516](https://github.com/pingcap/tispark/pull/1516)

## [TiSpark 2.3.0] 2020-07-06
### New Features
- Support working with TiDB-3.1 and TiDB-4.0
- Support working with TiFlash
- Support directly writing data to TiKV
### Fixes
- Support new row format encoding [#1492](https://github.com/pingcap/tispark/pull/1492)
- Fix test: add TiFlash replica avaiable check [#1495](https://github.com/pingcap/tispark/pull/1495)
- Fix string type pushdown [#1500](https://github.com/pingcap/tispark/pull/1500)

## [TiSpark 2.3.0-rc.1] 2020-06-22
### Fixes
- Fix column name case bug [#1487](https://github.com/pingcap/tispark/pull/1487)
- Fix resolve current lock npe bug [#1485](https://github.com/pingcap/tispark/pull/1485)
- Fix resolve lock bug with tiflash [#1483](https://github.com/pingcap/tispark/pull/1483)

## [TiSpark 2.3.0-rc] 2020-06-05
### New Features
- Support working with TiDB-3.1 and TiDB-4.0
- Support working with TiFlash
- Support directly writing data to TiKV

## [TiSpark 2.1.9] 2020-05-11
### Fixes
- Fix desc temp view [#1328](https://github.com/pingcap/tispark/pull/1328)
- Fix prefix index on blob [#1334](https://github.com/pingcap/tispark/pull/1334)
- Shade io.opencensus to resolve grpc conflict [#1352](https://github.com/pingcap/tispark/pull/1352)
- Fix parition table isn't shown in show command [#1374](https://github.com/pingcap/tispark/pull/1374)
- Fix partition pruning when partition definition contains big integer [#1385](https://github.com/pingcap/tispark/pull/1385)
- Support TiDB-4.0 [#1398](https://github.com/pingcap/tispark/pull/1398)

## [TiSpark 2.1.8] 2019-12-12
### Fixes
- Fix UnsupportedOperationException: using stream rather than removeIf [#1303](https://github.com/pingcap/tispark/pull/1303)

## [TiSpark 2.1.7] 2019-12-09
### Fixes
- Add task retry if tikv is down [#1207](https://github.com/pingcap/tispark/pull/1207)
- Fix output offsets: add field type to Constant and ColumnRef when encoding proto [#1231](https://github.com/pingcap/tispark/pull/1231)
- Register udf `ti_version` for every sparksession [#1258](https://github.com/pingcap/tispark/pull/1258)
- Add timezone check [#1275](https://github.com/pingcap/tispark/pull/1275)
- Disable set, enum and bit pushed down [#1242](https://github.com/pingcap/tispark/pull/1242)

## [TiSpark 2.1.6] 2019-11-08
### Fixes
- Fix TopN push down bug [#1185](https://github.com/pingcap/tispark/pull/1185)
- Consider nulls order in TopN pushdown [#1187](https://github.com/pingcap/tispark/pull/1187)
- Fix Stack Overflow Error when reading from partition table [#1179](https://github.com/pingcap/tispark/pull/1179)
- Fix parsing view table's json bug [#1174](https://github.com/pingcap/tispark/pull/1174)
- Fix No Matching column bug [#1162](https://github.com/pingcap/tispark/pull/1162)
- Fix behavior of estimateTableSize [#845](https://github.com/pingcap/tispark/pull/845)
- Fix Bit Type default value bug [#1148](https://github.com/pingcap/tispark/pull/1148)
- Fix fastxml security alert [#1127](https://github.com/pingcap/tispark/pull/1127)
- Fix bug: TiSpark Catalog has 10-20s delay [#1108](https://github.com/pingcap/tispark/pull/1108)
- Fix reading data from TiDB in Spark Structured Streaming [#1104](https://github.com/pingcap/tispark/pull/1104)

## [TiSpark 2.1.5] 2019-09-02
### Fixes
- Remove useless scala and jackson dependencies [#1079](https://github.com/pingcap/tispark/pull/1079)
- Fix range partition throw UnsupportedSyntaxException error [#1088](https://github.com/pingcap/tispark/pull/1088)
- Make TiSpark reading data from a hash partition table [#1089](https://github.com/pingcap/tispark/pull/1089)

## [TiSpark 2.2.0] 2019-08-30
### New Features
* Natively support writing data to TiKV (ACID) using Spark Data Source API

### WARNING
**DO NOT set `spark.tispark.write.without_lock_table` to `true` on production environment (you may lost data).**

### Improvements
* Release one TiSpark jar (both support Spark-2.3.x and Spark-2.4.x) instead of two [#933](https://github.com/pingcap/tispark/pull/933)
* Add spark version to TiSpark's udf ti_version [#943](https://github.com/pingcap/tispark/pull/943)
* Bump grpc to 1.17 [#982](https://github.com/pingcap/tispark/pull/982)
* Add retry mechanism for `batchGet` [#986](https://github.com/pingcap/tispark/pull/986)

### Fixes
* Catch UnsupportedSyntaxException when generating partition expressions [#960](https://github.com/pingcap/tispark/pull/960)
* Fix TiSpark cannot read from a hash partition table [#966](https://github.com/pingcap/tispark/pull/966)
* Prohibit extra index data type pushdown when doing index scan to avoid decoding extra column [#995](https://github.com/pingcap/tispark/pull/995)
* Prohibit agg or groupby pushdown on double read [#1004](https://github.com/pingcap/tispark/pull/1004)

## [TiSpark 2.1.4] 2019-08-27
### Fixes
- Fix distinct without alias bug: disable pushdown aggregate with alias [#1055](https://github.com/pingcap/tispark/pull/1055)
- Fix reflection bug: pass in different arguments for different version of same function [#1037](https://github.com/pingcap/tispark/pull/1037)

## [TiSpark 2.1.3] 2019-08-15
### Fixes
- Fix cost model in table scan [#1023](https://github.com/pingcap/tispark/pull/1023)
- Fix index scan bug [#1024](https://github.com/pingcap/tispark/pull/1024)
- Prohibit aggregate or group by pushdown on double read [#1027](https://github.com/pingcap/tispark/pull/1027)
- Fix reflection bug for HDP release [#1017](https://github.com/pingcap/tispark/pull/1017)
- Fix scala compiler version [#1019](https://github.com/pingcap/tispark/pull/1019)

## [TiSpark 2.1.2] 2019-07-29
### Fixes
* Fix improper response with region error [#922](https://github.com/pingcap/tispark/pull/922)
* Fix view parsing problem [#953](https://github.com/pingcap/tispark/pull/953)

## [TiSpark 1.2.1]
### Fixes
* Fix count error, if advanceNextResponse is empty, we should read next region (#899)
* Use fixed version of proto (#898)

## [TiSpark 2.1.1]
### Fixes
* Add TiDB/TiKV/PD version and Spark version supported for each latest major release (#804) (#887)
* Fix incorrect timestamp of tidbMapDatabase (#862) (#885)
* Fix column size estimation (#858) (#884)
* Fix count error, if advanceNextResponse is empty, we should read next region (#878) (#882)
* Use fixed version of proto instead of master branch (#843) (#850)

## [TiSpark 2.1]
### Features
* Support range partition pruning (Beta) (#599)
* Support show columns command (#614)

### Fixes
* Fix build key ranges with xor expression (#576)
* Fix cannot initialize pd if using ipv6 address (#587)
* Fix default value bug (#596)
* Fix possible IndexOutOfBoundException in KeyUtils (#597)
* Fix outputOffset is incorrect when building DAGRequest (#615)
* Fix incorrect implementation of Key.next() (#648)
* Fix partition parser can't parser numerical value 0 (#651)
* Fix prefix length may be larger than the value used. (#668)
* Fix retry logic when scan meet lock (#666)
* Fix inconsistent timestamp (#676)
* Fix tempView may be unresolved when applying timestamp to plan (#690)
* Fix concurrent DAGRequest issue (#714)
* Fix downgrade scan logic (#725)
* Fix integer type default value should be parsed to long (#741)
* Fix index scan on partition table (#735)
* Fix KeyNotInRegion may occur when retrieving rows by handle (#755)
* Fix encode value long max (#761)
* Fix MatchErrorException may occur when Unsigned BigInt contains in group by columns (#780)
* Fix IndexOutOfBoundException when trying to get pd member (#788)

## [TiSpark 2.0]
### Features
* Work with Spark 2.3
* Support use `$database` statement
* Support show databases statement
* Support show tables statement
* No need to use `TiContext.mapTiDBDatabase`, use `$database.$table` to identify a table instead
* Support data type SET and ENUM
* Support data type YEAR
* Support data type TIME
* Support isolation level settings
* Support describe table command
* Support cache tables and uncache tables
* Support read from a TiDB partition table
* Support use TiDB as metastore

### Fixes
* Fix JSON parsing (#491)
* Fix count on empty table (#498)
* Fix ScanIterator unable to read from adjacent empty regions (#519)
* Fix possible NullPointerException when setting show_row_id true (#522)

### Improved
* Make ti version usable without selecting database (#545)

## [TiSpark 1.2]
### Fixes
* Fixes compatibility with PDServer #480

## [TiSpark 1.1]
### Fixes multiple bugs:
* Fix daylight saving time (DST) (#347)
* Fix count(1) result is always 0 if subquery contains limit (#346)
* Fix incorrect totalRowCount calculation (#353)
* Fix request fail with Key not in region after retrying NotLeaderError (#354)
* Fix ScanIterator logic where index may be out of bound (#357)
* Fix tispark-sql dbName (#379)
* Fix StoreNotMatch (#396)
* Fix utf8 prefix index (#400)
* Fix decimal decoding (#401)
* Refactor not leader logic (#412)
* Fix global temp view not visible in thriftserver (#437)

### Adds:
* Allow TiSpark retrieve row id (#367)
* Decode json to string (#417)

### Improvements:
* Improve PD connection issue's error log (#388)
* Add DB prefix option for TiDB tables (#416)

## [TiSpark 1.0.1]
* Fix unsigned index
* Compatible with TiDB before and since 48a42f

## [TiSpark 1.0 GA]
### New Features
TiSpark provides distributed computing of TiDB data using Apache Spark.

* Provide a gRPC communication framework to read data from TiKV
* Provide encoding and decoding of TiKV component data and communication protocol
* Provide calculation pushdown, which includes:
    - Aggregate pushdown
    - Predicate pushdown
    - TopN pushdown
    - Limit pushdown
* Provide index related support
    - Transform predicate into Region key range or secondary index
    - Optimize Index Only queries
    - Adaptive downgrade index scan to table scan per region
* Provide cost-based optimization
    - Support statistics
    - Select index
    - Estimate broadcast table cost
* Provide support for multiple Spark interfaces
    - Support Spark Shell
    - Support ThriftServer/JDBC
    - Support Spark-SQL interaction
    - Support PySpark Shell
    - Support SparkR
