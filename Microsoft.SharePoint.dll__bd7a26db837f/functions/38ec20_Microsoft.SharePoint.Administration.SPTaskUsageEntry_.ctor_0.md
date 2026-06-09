# Microsoft.SharePoint.Administration.SPTaskUsageEntry::.ctor_0

- ea: `0x38ec20`
- end: `0x38edd8`
- name: `Microsoft.SharePoint.Administration.SPTaskUsageEntry::.ctor_0`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x38ede0`

## callees

- `0x2060c0`

## string_xrefs

- `0x38ec5e`: `ServiceCallCount`
- `0x38ec70`: `ServiceCallDurationSum`
- `0x38edc6`: `ProcessId`
- `0x38eca6`: `SqlLogicalReads`
- `0x38ecca`: `DistributedCacheReads`
- `0x38ecdc`: `DistributedCacheReadsDuration`
- `0x38ecee`: `DistributedCacheReadsSize`
- `0x38ed00`: `DistributedCacheWrites`
- `0x38ed12`: `DistributedCacheWritesDuration`
- `0x38ed24`: `DistributedCacheWritesSize`
- `0x38ed36`: `DistributedCacheMisses`
- `0x38ed48`: `DistributedCacheHits`
- `0x38ed5a`: `DistributedCacheFailures`
- `0x38ed6c`: `DistributedCachedObjectsRequested`

## pseudocode

```c

```

## disassembly

```asm
0x38ec20  ldarg.0
0x38ec21  ldarg.1
0x38ec22  call     instance void Microsoft.SharePoint.Administration.SPUsageEntry::.ctor(class Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo info)
0x38ec27  ldarg.1
0x38ec28  ldstr    aRequestcount// "RequestCount"
0x38ec2d  ldarg.0
0x38ec2e  ldflda   int16 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Requests
0x38ec33  callvirt T0x2B000295
0x38ec38  pop
0x38ec39  ldarg.1
0x38ec3a  ldstr    aQuerycount// "QueryCount"
0x38ec3f  ldarg.0
0x38ec40  ldflda   int16 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Queries
0x38ec45  callvirt T0x2B000295
0x38ec4a  pop
0x38ec4b  ldarg.1
0x38ec4c  ldstr    aQuerydurations// "QueryDurationSum"
0x38ec51  ldarg.0
0x38ec52  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_QueryDurationSum
0x38ec57  callvirt T0x2B000271
0x38ec5c  pop
0x38ec5d  ldarg.1
0x38ec5e  ldstr    aServicecallcou// "ServiceCallCount"
0x38ec63  ldarg.0
0x38ec64  ldflda   int16 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ServiceCalls
0x38ec69  callvirt T0x2B000295
0x38ec6e  pop
0x38ec6f  ldarg.1
0x38ec70  ldstr    aServicecalldur// "ServiceCallDurationSum"
0x38ec75  ldarg.0
0x38ec76  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ServiceCallDurationSum
0x38ec7b  callvirt T0x2B000271
0x38ec80  pop
0x38ec81  ldarg.1
0x38ec82  ldstr    aDuration// "Duration"
0x38ec87  ldarg.0
0x38ec88  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Duration
0x38ec8d  callvirt T0x2B000271
0x38ec92  pop
0x38ec93  ldarg.1
0x38ec94  ldstr    aTitle_0// "Title"
0x38ec99  ldarg.0
0x38ec9a  ldflda   string Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Title
0x38ec9f  callvirt T0x2B0000FD
0x38eca4  pop
0x38eca5  ldarg.1
0x38eca6  ldstr    aSqllogicalread// "SqlLogicalReads"
0x38ecab  ldarg.0
0x38ecac  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_SqlLogicalReads
0x38ecb1  callvirt T0x2B000271
0x38ecb6  pop
0x38ecb7  ldarg.1
0x38ecb8  ldstr    aCpumcycles// "CPUMCycles"
0x38ecbd  ldarg.0
0x38ecbe  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_CPUMCycles
0x38ecc3  callvirt T0x2B000271
0x38ecc8  pop
0x38ecc9  ldarg.1
0x38ecca  ldstr    aDistributedcac_0// "DistributedCacheReads"
0x38eccf  ldarg.0
0x38ecd0  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheReads
0x38ecd5  callvirt T0x2B000271
0x38ecda  pop
0x38ecdb  ldarg.1
0x38ecdc  ldstr    aDistributedcac_1// "DistributedCacheReadsDuration"
0x38ece1  ldarg.0
0x38ece2  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheReadsDuration
0x38ece7  callvirt T0x2B000271
0x38ecec  pop
0x38eced  ldarg.1
0x38ecee  ldstr    aDistributedcac_2// "DistributedCacheReadsSize"
0x38ecf3  ldarg.0
0x38ecf4  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheReadsSize
0x38ecf9  callvirt T0x2B000271
0x38ecfe  pop
0x38ecff  ldarg.1
0x38ed00  ldstr    aDistributedcac_3// "DistributedCacheWrites"
0x38ed05  ldarg.0
0x38ed06  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheWrites
0x38ed0b  callvirt T0x2B000271
0x38ed10  pop
0x38ed11  ldarg.1
0x38ed12  ldstr    aDistributedcac_4// "DistributedCacheWritesDuration"
0x38ed17  ldarg.0
0x38ed18  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheWritesDuration
0x38ed1d  callvirt T0x2B000271
0x38ed22  pop
0x38ed23  ldarg.1
0x38ed24  ldstr    aDistributedcac_5// "DistributedCacheWritesSize"
0x38ed29  ldarg.0
0x38ed2a  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheWritesSize
0x38ed2f  callvirt T0x2B000271
0x38ed34  pop
0x38ed35  ldarg.1
0x38ed36  ldstr    aDistributedcac_6// "DistributedCacheMisses"
0x38ed3b  ldarg.0
0x38ed3c  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheMisses
0x38ed41  callvirt T0x2B000271
0x38ed46  pop
0x38ed47  ldarg.1
0x38ed48  ldstr    aDistributedcac_7// "DistributedCacheHits"
0x38ed4d  ldarg.0
0x38ed4e  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheHits
0x38ed53  callvirt T0x2B000271
0x38ed58  pop
0x38ed59  ldarg.1
0x38ed5a  ldstr    aDistributedcac_8// "DistributedCacheFailures"
0x38ed5f  ldarg.0
0x38ed60  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheFailures
0x38ed65  callvirt T0x2B000271
0x38ed6a  pop
0x38ed6b  ldarg.1
0x38ed6c  ldstr    aDistributedcac_9// "DistributedCachedObjectsRequested"
0x38ed71  ldarg.0
0x38ed72  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCachedObjectsRequested
0x38ed77  callvirt T0x2B000271
0x38ed7c  pop
0x38ed7d  ldarg.1
0x38ed7e  ldstr    aManagedmemoryb// "ManagedMemoryBytes"
0x38ed83  ldarg.0
0x38ed84  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ManagedMemoryBytes
0x38ed89  callvirt T0x2B000131
0x38ed8e  pop
0x38ed8f  ldarg.1
0x38ed90  ldstr    aManagedmemoryb_0// "ManagedMemoryBytesLOH"
0x38ed95  ldarg.0
0x38ed96  ldflda   valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ManagedMemoryBytesLOH
0x38ed9b  callvirt T0x2B000131
0x38eda0  pop
0x38eda1  ldarg.1
0x38eda2  ldstr    aCpuduration_0// "CPUDuration"
0x38eda7  ldarg.0
0x38eda8  ldflda   int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_CPUDuration
0x38edad  callvirt T0x2B000271
0x38edb2  pop
0x38edb3  ldarg.1
0x38edb4  ldstr    aProcessname// "ProcessName"
0x38edb9  ldarg.0
0x38edba  ldflda   string Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ProcessName
0x38edbf  callvirt T0x2B0000FD
0x38edc4  pop
0x38edc5  ldarg.1
0x38edc6  ldstr    aProcessid// "ProcessId"
0x38edcb  ldarg.0
0x38edcc  ldflda   int32 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ProcessId
0x38edd1  callvirt T0x2B00012C
0x38edd6  pop
0x38edd7  ret
```
