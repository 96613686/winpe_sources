# Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveDistributedCachePerformanceCounters

- ea: `0x65f6c0`
- end: `0x65f838`
- name: `Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveDistributedCachePerformanceCounters`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x65f210`
- `0x65f2a0`

## string_xrefs

- `0x65f7b0`: `AppFabric Caching:Cache`
- `0x65f7bf`: `AppFabric Caching:Cache`
- `0x65f7ce`: `AppFabric Caching:Cache`
- `0x65f7dd`: `AppFabric Caching:Cache`
- `0x65f7ec`: `AppFabric Caching:Cache`
- `0x65f7fb`: `AppFabric Caching:Cache`
- `0x65f80a`: `AppFabric Caching:Cache`
- `0x65f819`: `AppFabric Caching:Cache`
- `0x65f828`: `AppFabric Caching:Cache`
- `0x65f6c5`: `DistributedCacheService`
- `0x65f6d4`: `DistributedCacheService`
- `0x65f6e3`: `DistributedCacheService`
- `0x65f6f2`: `Total Cache Misses`
- `0x65f7b5`: `Total Cache Misses`
- `0x65f701`: `Cache Miss Percentage`
- `0x65f7c4`: `Cache Miss Percentage`
- `0x65f779`: `Total Read Requests`
- `0x65f800`: `Total Read Requests`
- `0x65f788`: `Total Read Requests /sec`
- `0x65f80f`: `Total Read Requests /sec`
- `0x65f797`: `Total Write Operations`
- `0x65f81e`: `Total Write Operations`
- `0x65f7a6`: `Total Write Operations /sec`
- `0x65f82d`: `Total Write Operations /sec`

## pseudocode

```c

```

## disassembly

```asm
0x65f6c0  ldstr    aNetClrMemory// ".NET CLR Memory"
0x65f6c5  ldstr    aDistributedcac_10// "DistributedCacheService"
0x65f6ca  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveInstance(string category, string instance)
0x65f6cf  ldstr    aProcess_0// "Process"
0x65f6d4  ldstr    aDistributedcac_10// "DistributedCacheService"
0x65f6d9  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveInstance(string category, string instance)
0x65f6de  ldstr    aProcessor_2// "Processor"
0x65f6e3  ldstr    aDistributedcac_10// "DistributedCacheService"
0x65f6e8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveInstance(string category, string instance)
0x65f6ed  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f6f2  ldstr    aTotalCacheMiss// "Total Cache Misses"
0x65f6f7  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f6fc  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f701  ldstr    aCacheMissPerce// "Cache Miss Percentage"
0x65f706  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f70b  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f710  ldstr    aTotalDataSizeB// "Total Data Size Bytes"
0x65f715  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f71a  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f71f  ldstr    aTotalEvictedOb// "Total Evicted Objects"
0x65f724  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f729  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f72e  ldstr    aTotalEvictionR// "Total Eviction Runs"
0x65f733  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f738  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f73d  ldstr    aTotalExpiredOb// "Total Expired Objects"
0x65f742  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f747  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f74c  ldstr    aTotalMemoryEvi// "Total Memory Evicted"
0x65f751  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f756  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f75b  ldstr    aTotalObjectCou// "Total Object Count"
0x65f760  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f765  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f76a  ldstr    aTotalObjectsRe// "Total Objects Returned"
0x65f76f  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f774  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f779  ldstr    aTotalReadReque// "Total Read Requests"
0x65f77e  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f783  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f788  ldstr    aTotalReadReque_0// "Total Read Requests /sec"
0x65f78d  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f792  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f797  ldstr    aTotalWriteOper// "Total Write Operations"
0x65f79c  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7a1  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f7a6  ldstr    aTotalWriteOper_0// "Total Write Operations /sec"
0x65f7ab  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7b0  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f7b5  ldstr    aTotalCacheMiss// "Total Cache Misses"
0x65f7ba  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7bf  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f7c4  ldstr    aCacheMissPerce// "Cache Miss Percentage"
0x65f7c9  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7ce  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f7d3  ldstr    aTotalDataSizeB// "Total Data Size Bytes"
0x65f7d8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7dd  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f7e2  ldstr    aTotalObjectCou// "Total Object Count"
0x65f7e7  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7ec  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f7f1  ldstr    aTotalObjectsRe// "Total Objects Returned"
0x65f7f6  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f7fb  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f800  ldstr    aTotalReadReque// "Total Read Requests"
0x65f805  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f80a  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f80f  ldstr    aTotalReadReque_0// "Total Read Requests /sec"
0x65f814  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f819  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f81e  ldstr    aTotalWriteOper// "Total Write Operations"
0x65f823  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f828  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f82d  ldstr    aTotalWriteOper_0// "Total Write Operations /sec"
0x65f832  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::RemoveCounter(string category, string counter)
0x65f837  ret
```
