# Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddDistributedCachePerformanceCounters

- ea: `0x65f3c0`
- end: `0x65f6be`
- name: `Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddDistributedCachePerformanceCounters`
- size: `766`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c8720`
- `0x1c89b0`
- `0x29d0f0`
- `0x65f0d0`
- `0x65f170`
- `0x65f3c0`

## string_xrefs

- `0x65f5ed`: `AppFabric Caching:Cache`
- `0x65f5fd`: `AppFabric Caching:Cache`
- `0x65f60d`: `AppFabric Caching:Cache`
- `0x65f61d`: `AppFabric Caching:Cache`
- `0x65f62d`: `AppFabric Caching:Cache`
- `0x65f63d`: `AppFabric Caching:Cache`
- `0x65f64d`: `AppFabric Caching:Cache`
- `0x65f65d`: `AppFabric Caching:Cache`
- `0x65f66d`: `AppFabric Caching:Cache`
- `0x65f67d`: `AppFabric Caching:Cache`
- `0x65f68d`: `AppFabric Caching:Cache`
- `0x65f69d`: `AppFabric Caching:Cache`
- `0x65f6ad`: `AppFabric Caching:Cache`
- `0x65f42b`: `DistributedCacheService`
- `0x65f43f`: `DistributedCacheService`
- `0x65f453`: `DistributedCacheService`
- `0x65f462`: `Total Cache Misses`
- `0x65f5f2`: `Total Cache Misses`
- `0x65f472`: `Cache Miss Percentage`
- `0x65f602`: `Cache Miss Percentage`
- `0x65f4f2`: `Total Read Requests`
- `0x65f642`: `Total Read Requests`
- `0x65f502`: `Total Read Requests /sec`
- `0x65f652`: `Total Read Requests /sec`
- `0x65f512`: `Total Write Operations`
- `0x65f662`: `Total Write Operations`
- `0x65f522`: `Total Write Operations /sec`
- `0x65f672`: `Total Write Operations /sec`
- `0x65f682`: `Total Cache Misses /sec`

## pseudocode

```c

```

## disassembly

```asm
0x65f3c0  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x65f3c5  stloc.0
0x65f3c6  ldloc.0
0x65f3c7  ldnull
0x65f3c8  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x65f3cd  brtrue.s loc_65F421
0x65f3cf  ldloc.0
0x65f3d0  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x65f3d5  ldstr    aDonotstoreperf// "DoNotStorePerfCountersInUsageDB"
0x65f3da  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x65f3df  brfalse.s loc_65F421
0x65f3e1  ldloc.0
0x65f3e2  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x65f3e7  ldstr    aDonotstoreperf// "DoNotStorePerfCountersInUsageDB"
0x65f3ec  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x65f3f1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x65f3f6  ldtoken  [mscorlib]System.Boolean
0x65f3fb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x65f400  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x65f405  brtrue.s loc_65F421
0x65f407  ldloc.0
0x65f408  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x65f40d  ldstr    aDonotstoreperf// "DoNotStorePerfCountersInUsageDB"
0x65f412  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x65f417  unbox.any [mscorlib]System.Boolean
0x65f41c  brtrue   loc_65F6BD
0x65f421  ldstr    aNetClrMemory// ".NET CLR Memory"
0x65f426  ldstr    aTimeInGc// "% Time in GC"
0x65f42b  ldstr    aDistributedcac_10// "DistributedCacheService"
0x65f430  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddInstance(string category, string counter, string instance)
0x65f435  ldstr    aProcess_0// "Process"
0x65f43a  ldstr    aWorkingSet// "Working Set"
0x65f43f  ldstr    aDistributedcac_10// "DistributedCacheService"
0x65f444  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddInstance(string category, string counter, string instance)
0x65f449  ldstr    aProcessor_2// "Processor"
0x65f44e  ldstr    aTimeInGc// "% Time in GC"
0x65f453  ldstr    aDistributedcac_10// "DistributedCacheService"
0x65f458  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddInstance(string category, string counter, string instance)
0x65f45d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f462  ldstr    aTotalCacheMiss// "Total Cache Misses"
0x65f467  ldc.i4.0
0x65f468  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f46d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f472  ldstr    aCacheMissPerce// "Cache Miss Percentage"
0x65f477  ldc.i4.0
0x65f478  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f47d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f482  ldstr    aTotalDataSizeB// "Total Data Size Bytes"
0x65f487  ldc.i4.0
0x65f488  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f48d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f492  ldstr    aTotalEvictedOb// "Total Evicted Objects"
0x65f497  ldc.i4.0
0x65f498  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f49d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f4a2  ldstr    aTotalEvictionR// "Total Eviction Runs"
0x65f4a7  ldc.i4.0
0x65f4a8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f4ad  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f4b2  ldstr    aTotalExpiredOb// "Total Expired Objects"
0x65f4b7  ldc.i4.0
0x65f4b8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f4bd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f4c2  ldstr    aTotalMemoryEvi// "Total Memory Evicted"
0x65f4c7  ldc.i4.0
0x65f4c8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f4cd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f4d2  ldstr    aTotalObjectCou// "Total Object Count"
0x65f4d7  ldc.i4.0
0x65f4d8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f4dd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f4e2  ldstr    aTotalObjectsRe// "Total Objects Returned"
0x65f4e7  ldc.i4.0
0x65f4e8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f4ed  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f4f2  ldstr    aTotalReadReque// "Total Read Requests"
0x65f4f7  ldc.i4.0
0x65f4f8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f4fd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f502  ldstr    aTotalReadReque_0// "Total Read Requests /sec"
0x65f507  ldc.i4.0
0x65f508  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f50d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f512  ldstr    aTotalWriteOper// "Total Write Operations"
0x65f517  ldc.i4.0
0x65f518  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f51d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f522  ldstr    aTotalWriteOper_0// "Total Write Operations /sec"
0x65f527  ldc.i4.0
0x65f528  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f52d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f532  ldstr    aTotalRetryExce// "Total Retry Exception"
0x65f537  ldc.i4.0
0x65f538  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f53d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f542  ldstr    aTotalRetryExce_0// "Total Retry Exception /sec"
0x65f547  ldc.i4.0
0x65f548  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f54d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f552  ldstr    aTotalFailureEx_0// "Total Failure Exceptions"
0x65f557  ldc.i4.0
0x65f558  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f55d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f562  ldstr    aTotalFailureEx// "Total Failure Exceptions /sec"
0x65f567  ldc.i4.0
0x65f568  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f56d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f572  ldstr    aTotalGetMisses// "Total Get Misses"
0x65f577  ldc.i4.0
0x65f578  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f57d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f582  ldstr    aTotalGetMisses_0// "Total Get Misses /sec"
0x65f587  ldc.i4.0
0x65f588  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f58d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f592  ldstr    aTotalGetReques// "Total Get Requests"
0x65f597  ldc.i4.0
0x65f598  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f59d  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f5a2  ldstr    aTotalGetReques_0// "Total Get Requests /sec"
0x65f5a7  ldc.i4.0
0x65f5a8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f5ad  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f5b2  ldstr    aTotalClientReq// "Total Client Requests"
0x65f5b7  ldc.i4.0
0x65f5b8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f5bd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f5c2  ldstr    aTotalClientReq_0// "Total Client Requests /sec"
0x65f5c7  ldc.i4.0
0x65f5c8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f5cd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f5d2  ldstr    aTotalRequestsS_0// "Total Requests Served"
0x65f5d7  ldc.i4.0
0x65f5d8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f5dd  ldstr    aAppfabricCachi// "AppFabric Caching:Host"
0x65f5e2  ldstr    aTotalRequestsS// "Total Requests Served /sec"
0x65f5e7  ldc.i4.0
0x65f5e8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f5ed  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f5f2  ldstr    aTotalCacheMiss// "Total Cache Misses"
0x65f5f7  ldc.i4.1
0x65f5f8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f5fd  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f602  ldstr    aCacheMissPerce// "Cache Miss Percentage"
0x65f607  ldc.i4.1
0x65f608  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f60d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f612  ldstr    aTotalDataSizeB// "Total Data Size Bytes"
0x65f617  ldc.i4.1
0x65f618  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f61d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f622  ldstr    aTotalObjectCou// "Total Object Count"
0x65f627  ldc.i4.1
0x65f628  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f62d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f632  ldstr    aTotalObjectsRe// "Total Objects Returned"
0x65f637  ldc.i4.1
0x65f638  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f63d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f642  ldstr    aTotalReadReque// "Total Read Requests"
0x65f647  ldc.i4.1
0x65f648  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f64d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f652  ldstr    aTotalReadReque_0// "Total Read Requests /sec"
0x65f657  ldc.i4.1
0x65f658  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f65d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f662  ldstr    aTotalWriteOper// "Total Write Operations"
0x65f667  ldc.i4.1
0x65f668  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f66d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f672  ldstr    aTotalWriteOper_0// "Total Write Operations /sec"
0x65f677  ldc.i4.1
0x65f678  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f67d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f682  ldstr    aTotalCacheMiss_0// "Total Cache Misses /sec"
0x65f687  ldc.i4.1
0x65f688  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f68d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f692  ldstr    aTotalClientReq_0// "Total Client Requests /sec"
0x65f697  ldc.i4.1
0x65f698  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f69d  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f6a2  ldstr    aTotalClientReq// "Total Client Requests"
0x65f6a7  ldc.i4.1
0x65f6a8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f6ad  ldstr    aAppfabricCachi_0// "AppFabric Caching:Cache"
0x65f6b2  ldstr    aTotalEvictionR// "Total Eviction Runs"
0x65f6b7  ldc.i4.1
0x65f6b8  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCachePerfCounterHelper::AddCounter(string category, string counter, bool addAllInstances)
0x65f6bd  ret
```
