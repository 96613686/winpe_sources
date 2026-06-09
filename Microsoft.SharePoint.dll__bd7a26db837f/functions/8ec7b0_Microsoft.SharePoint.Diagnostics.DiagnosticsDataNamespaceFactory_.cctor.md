# Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::.cctor

- ea: `0x8ec7b0`
- end: `0x8ecbc9`
- name: `Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::.cctor`
- size: `1049`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ec750`

## string_xrefs

- `0x8ecb0c`: `ReadBlobBytes`
- `0x8ec942`: `SPDistributedCache`
- `0x8ec964`: `SPDistributedCache`
- `0x8ec986`: `SPDistributedCache`
- `0x8ec9a8`: `SPDistributedCache`
- `0x8ec9ca`: `SPDistributedCache`
- `0x8ec9ec`: `SPDistributedCache`
- `0x8eca0e`: `SPDistributedCache`
- `0x8eca30`: `SPDistributedCache`
- `0x8eca52`: `SPDistributedCache`
- `0x8eca74`: `SPDistributedCache`
- `0x8ec816`: `ServiceCall`
- `0x8ec835`: `ServiceCall`
- `0x8ec8fe`: `NumLogicalReads`
- `0x8ec930`: `NumLogicalReads`
- `0x8ec952`: `TotalCacheReads`
- `0x8ec974`: `TotalCacheWrites`
- `0x8ec996`: `TotalCacheReadsDuration`
- `0x8ec9b8`: `TotalCacheWritesDuration`
- `0x8ec9da`: `TotalCacheWritesSize`
- `0x8ec9fc`: `TotalCacheReadsSize`
- `0x8eca1e`: `TotalCacheMisses`
- `0x8eca40`: `TotalCacheHits`
- `0x8eca62`: `TotalCacheFailures`
- `0x8eca84`: `TotalCachedObjectsRequested`
- `0x8ecaea`: `ReadBlobs`
- `0x8ecb2e`: `EffectiveReadBlobs`
- `0x8ecbb6`: `DeletedBlobs`

## pseudocode

```c

```

## disassembly

```asm
0x8ec7b0  ldstr    aOutboundcallto// "OutboundCallTotalCount"
0x8ec7b5  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::OutboundCallTotalCount
0x8ec7ba  ldstr    aOutboundcallto_0// "OutboundCallTotalDuration"
0x8ec7bf  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::OutboundCallTotalDuration
0x8ec7c4  ldstr    aOutboundcallsl// "OutboundCallSlowestName"
0x8ec7c9  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::OutboundCallSlowestName
0x8ec7ce  ldstr    aOutboundcallsl_0// "OutboundCallSlowestDuration"
0x8ec7d3  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::OutboundCallSlowestDuration
0x8ec7d8  ldstr    aSqlquery// "SqlQuery"
0x8ec7dd  ldc.i4.1
0x8ec7de  newarr   [mscorlib]System.String
0x8ec7e3  stloc.0
0x8ec7e4  ldloc.0
0x8ec7e5  ldc.i4.0
0x8ec7e6  ldstr    aTotalduration// "TotalDuration"
0x8ec7eb  stelem.ref
0x8ec7ec  ldloc.0
0x8ec7ed  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec7f2  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SqlQueryTotalDuration
0x8ec7f7  ldstr    aSqlquery// "SqlQuery"
0x8ec7fc  ldc.i4.1
0x8ec7fd  newarr   [mscorlib]System.String
0x8ec802  stloc.1
0x8ec803  ldloc.1
0x8ec804  ldc.i4.0
0x8ec805  ldstr    aTotalcount// "TotalCount"
0x8ec80a  stelem.ref
0x8ec80b  ldloc.1
0x8ec80c  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec811  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SqlQueryCount
0x8ec816  ldstr    aServicecall// "ServiceCall"
0x8ec81b  ldc.i4.1
0x8ec81c  newarr   [mscorlib]System.String
0x8ec821  stloc.2
0x8ec822  ldloc.2
0x8ec823  ldc.i4.0
0x8ec824  ldstr    aTotalduration// "TotalDuration"
0x8ec829  stelem.ref
0x8ec82a  ldloc.2
0x8ec82b  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec830  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::ServiceCallTotalDuration
0x8ec835  ldstr    aServicecall// "ServiceCall"
0x8ec83a  ldc.i4.1
0x8ec83b  newarr   [mscorlib]System.String
0x8ec840  stloc.3
0x8ec841  ldloc.3
0x8ec842  ldc.i4.0
0x8ec843  ldstr    aTotalcount// "TotalCount"
0x8ec848  stelem.ref
0x8ec849  ldloc.3
0x8ec84a  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec84f  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::ServiceCallCount
0x8ec854  ldstr    aLockwait// "LockWait"
0x8ec859  ldc.i4.1
0x8ec85a  newarr   [mscorlib]System.String
0x8ec85f  stloc.s  4
0x8ec861  ldloc.s  4
0x8ec863  ldc.i4.0
0x8ec864  ldstr    aTotalduration// "TotalDuration"
0x8ec869  stelem.ref
0x8ec86a  ldloc.s  4
0x8ec86c  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec871  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::LockWaitTotalDuration
0x8ec876  ldstr    aLockwait// "LockWait"
0x8ec87b  ldc.i4.1
0x8ec87c  newarr   [mscorlib]System.String
0x8ec881  stloc.s  5
0x8ec883  ldloc.s  5
0x8ec885  ldc.i4.0
0x8ec886  ldstr    aTotalcount// "TotalCount"
0x8ec88b  stelem.ref
0x8ec88c  ldloc.s  5
0x8ec88e  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec893  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::LockWaitCount
0x8ec898  ldstr    aSprequest// "SPRequest"
0x8ec89d  ldc.i4.1
0x8ec89e  newarr   [mscorlib]System.String
0x8ec8a3  stloc.s  6
0x8ec8a5  ldloc.s  6
0x8ec8a7  ldc.i4.0
0x8ec8a8  ldstr    aTotalcount// "TotalCount"
0x8ec8ad  stelem.ref
0x8ec8ae  ldloc.s  6
0x8ec8b0  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec8b5  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPRequestCount
0x8ec8ba  ldstr    aCriticaltrace// "CriticalTrace"
0x8ec8bf  ldc.i4.1
0x8ec8c0  newarr   [mscorlib]System.String
0x8ec8c5  stloc.s  7
0x8ec8c7  ldloc.s  7
0x8ec8c9  ldc.i4.0
0x8ec8ca  ldstr    aTotalcount// "TotalCount"
0x8ec8cf  stelem.ref
0x8ec8d0  ldloc.s  7
0x8ec8d2  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec8d7  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::CriticalTraceCount
0x8ec8dc  ldstr    aCriticaltrace// "CriticalTrace"
0x8ec8e1  ldc.i4.1
0x8ec8e2  newarr   [mscorlib]System.String
0x8ec8e7  stloc.s  8
0x8ec8e9  ldloc.s  8
0x8ec8eb  ldc.i4.0
0x8ec8ec  ldstr    aTracemessages// "TraceMessages"
0x8ec8f1  stelem.ref
0x8ec8f2  ldloc.s  8
0x8ec8f4  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec8f9  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::CriticalTraceMessages
0x8ec8fe  ldstr    aNumlogicalread// "NumLogicalReads"
0x8ec903  ldc.i4.1
0x8ec904  newarr   [mscorlib]System.String
0x8ec909  stloc.s  9
0x8ec90b  ldloc.s  9
0x8ec90d  ldc.i4.0
0x8ec90e  ldstr    aTotalcount// "TotalCount"
0x8ec913  stelem.ref
0x8ec914  ldloc.s  9
0x8ec916  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec91b  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::NumOfLogicalReadsCount
0x8ec920  ldstr    aSqlquery// "SqlQuery"
0x8ec925  ldc.i4.1
0x8ec926  newarr   [mscorlib]System.String
0x8ec92b  stloc.s  0xA
0x8ec92d  ldloc.s  0xA
0x8ec92f  ldc.i4.0
0x8ec930  ldstr    aNumlogicalread// "NumLogicalReads"
0x8ec935  stelem.ref
0x8ec936  ldloc.s  0xA
0x8ec938  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec93d  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SqlQueryTotalLogicalReads
0x8ec942  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8ec947  ldc.i4.1
0x8ec948  newarr   [mscorlib]System.String
0x8ec94d  stloc.s  0xB
0x8ec94f  ldloc.s  0xB
0x8ec951  ldc.i4.0
0x8ec952  ldstr    aTotalcacheread// "TotalCacheReads"
0x8ec957  stelem.ref
0x8ec958  ldloc.s  0xB
0x8ec95a  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec95f  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheTotalReads
0x8ec964  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8ec969  ldc.i4.1
0x8ec96a  newarr   [mscorlib]System.String
0x8ec96f  stloc.s  0xC
0x8ec971  ldloc.s  0xC
0x8ec973  ldc.i4.0
0x8ec974  ldstr    aTotalcachewrit// "TotalCacheWrites"
0x8ec979  stelem.ref
0x8ec97a  ldloc.s  0xC
0x8ec97c  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec981  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheTotalWrites
0x8ec986  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8ec98b  ldc.i4.1
0x8ec98c  newarr   [mscorlib]System.String
0x8ec991  stloc.s  0xD
0x8ec993  ldloc.s  0xD
0x8ec995  ldc.i4.0
0x8ec996  ldstr    aTotalcacheread_0// "TotalCacheReadsDuration"
0x8ec99b  stelem.ref
0x8ec99c  ldloc.s  0xD
0x8ec99e  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec9a3  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheReadsDuration
0x8ec9a8  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8ec9ad  ldc.i4.1
0x8ec9ae  newarr   [mscorlib]System.String
0x8ec9b3  stloc.s  0xE
0x8ec9b5  ldloc.s  0xE
0x8ec9b7  ldc.i4.0
0x8ec9b8  ldstr    aTotalcachewrit_0// "TotalCacheWritesDuration"
0x8ec9bd  stelem.ref
0x8ec9be  ldloc.s  0xE
0x8ec9c0  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec9c5  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheWritesDuration
0x8ec9ca  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8ec9cf  ldc.i4.1
0x8ec9d0  newarr   [mscorlib]System.String
0x8ec9d5  stloc.s  0xF
0x8ec9d7  ldloc.s  0xF
0x8ec9d9  ldc.i4.0
0x8ec9da  ldstr    aTotalcachewrit_1// "TotalCacheWritesSize"
0x8ec9df  stelem.ref
0x8ec9e0  ldloc.s  0xF
0x8ec9e2  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ec9e7  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheWritesSize
0x8ec9ec  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8ec9f1  ldc.i4.1
0x8ec9f2  newarr   [mscorlib]System.String
0x8ec9f7  stloc.s  0x10
0x8ec9f9  ldloc.s  0x10
0x8ec9fb  ldc.i4.0
0x8ec9fc  ldstr    aTotalcacheread_1// "TotalCacheReadsSize"
0x8eca01  stelem.ref
0x8eca02  ldloc.s  0x10
0x8eca04  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8eca09  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheReadsSize
0x8eca0e  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8eca13  ldc.i4.1
0x8eca14  newarr   [mscorlib]System.String
0x8eca19  stloc.s  0x11
0x8eca1b  ldloc.s  0x11
0x8eca1d  ldc.i4.0
0x8eca1e  ldstr    aTotalcachemiss// "TotalCacheMisses"
0x8eca23  stelem.ref
0x8eca24  ldloc.s  0x11
0x8eca26  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8eca2b  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheMisses
0x8eca30  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8eca35  ldc.i4.1
0x8eca36  newarr   [mscorlib]System.String
0x8eca3b  stloc.s  0x12
0x8eca3d  ldloc.s  0x12
0x8eca3f  ldc.i4.0
0x8eca40  ldstr    aTotalcachehits// "TotalCacheHits"
0x8eca45  stelem.ref
0x8eca46  ldloc.s  0x12
0x8eca48  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8eca4d  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheHits
0x8eca52  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8eca57  ldc.i4.1
0x8eca58  newarr   [mscorlib]System.String
0x8eca5d  stloc.s  0x13
0x8eca5f  ldloc.s  0x13
0x8eca61  ldc.i4.0
0x8eca62  ldstr    aTotalcachefail// "TotalCacheFailures"
0x8eca67  stelem.ref
0x8eca68  ldloc.s  0x13
0x8eca6a  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8eca6f  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCacheFailures
0x8eca74  ldstr    aSpdistributedc_6// "SPDistributedCache"
0x8eca79  ldc.i4.1
0x8eca7a  newarr   [mscorlib]System.String
0x8eca7f  stloc.s  0x14
0x8eca81  ldloc.s  0x14
0x8eca83  ldc.i4.0
0x8eca84  ldstr    aTotalcachedobj// "TotalCachedObjectsRequested"
0x8eca89  stelem.ref
0x8eca8a  ldloc.s  0x14
0x8eca8c  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8eca91  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::SPDistributedCachedObjectsRequested
0x8eca96  ldstr    aHostblobstore// "HostBlobStore"
0x8eca9b  ldc.i4.1
0x8eca9c  newarr   [mscorlib]System.String
0x8ecaa1  stloc.s  0x15
0x8ecaa3  ldloc.s  0x15
0x8ecaa5  ldc.i4.0
0x8ecaa6  ldstr    aChangequeriedb// "ChangeQueriedBlobs"
0x8ecaab  stelem.ref
0x8ecaac  ldloc.s  0x15
0x8ecaae  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ecab3  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::HBChangeQueriedBlobs
0x8ecab8  ldstr    aHostblobstore// "HostBlobStore"
0x8ecabd  ldc.i4.1
0x8ecabe  newarr   [mscorlib]System.String
0x8ecac3  stloc.s  0x16
0x8ecac5  ldloc.s  0x16
0x8ecac7  ldc.i4.0
0x8ecac8  ldstr    aChangequeriedb_0// "ChangeQueriedBlobBytes"
0x8ecacd  stelem.ref
0x8ecace  ldloc.s  0x16
0x8ecad0  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ecad5  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::HBChangeQueriedBlobBytes
0x8ecada  ldstr    aHostblobstore// "HostBlobStore"
0x8ecadf  ldc.i4.1
0x8ecae0  newarr   [mscorlib]System.String
0x8ecae5  stloc.s  0x17
0x8ecae7  ldloc.s  0x17
0x8ecae9  ldc.i4.0
0x8ecaea  ldstr    aReadblobs// "ReadBlobs"
0x8ecaef  stelem.ref
0x8ecaf0  ldloc.s  0x17
0x8ecaf2  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ecaf7  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::HBReadBlobs
0x8ecafc  ldstr    aHostblobstore// "HostBlobStore"
0x8ecb01  ldc.i4.1
0x8ecb02  newarr   [mscorlib]System.String
0x8ecb07  stloc.s  0x18
0x8ecb09  ldloc.s  0x18
0x8ecb0b  ldc.i4.0
0x8ecb0c  ldstr    aReadblobbytes// "ReadBlobBytes"
0x8ecb11  stelem.ref
0x8ecb12  ldloc.s  0x18
0x8ecb14  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ecb19  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::HBReadBlobBytes
0x8ecb1e  ldstr    aHostblobstore// "HostBlobStore"
0x8ecb23  ldc.i4.1
0x8ecb24  newarr   [mscorlib]System.String
0x8ecb29  stloc.s  0x19
0x8ecb2b  ldloc.s  0x19
0x8ecb2d  ldc.i4.0
0x8ecb2e  ldstr    aEffectivereadb_0// "EffectiveReadBlobs"
0x8ecb33  stelem.ref
0x8ecb34  ldloc.s  0x19
0x8ecb36  call     string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::BuildName(string namespaceName, string[] names)
0x8ecb3b  stsfld   string Microsoft.SharePoint.Diagnostics.DiagnosticsDataNamespaceFactory::HBEffectiveReadBlobBytes
0x8ecb40  ldstr    aHostblobstore// "HostBlobStore"
0x8ecb45  ldc.i4.1
0x8ecb46  newarr   [mscorlib]System.String
0x8ecb4b  stloc.s  0x1A
0x8ecb4d  ldloc.s  0x1A
0x8ecb4f  ldc.i4.0
  ... truncated ...
```
