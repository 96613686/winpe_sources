# Microsoft.SharePoint.Administration.SPTaskUsageEntry::Microsoft.SharePoint.Administration.ISerializableUsageEntry.GetObjectData

- ea: `0x38f240`
- end: `0x38f44e`
- name: `Microsoft.SharePoint.Administration.SPTaskUsageEntry::Microsoft.SharePoint.Administration.ISerializableUsageEntry.GetObjectData`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x2061f0`
- `0x7ae700`

## string_xrefs

- `0x38f28a`: `ServiceCallCount`
- `0x38f2a0`: `ServiceCallDurationSum`
- `0x38f438`: `ProcessId`
- `0x38f2dd`: `SqlLogicalReads`
- `0x38f309`: `DistributedCacheReads`
- `0x38f31f`: `DistributedCacheReadsDuration`
- `0x38f361`: `DistributedCacheReadsSize`
- `0x38f335`: `DistributedCacheWrites`
- `0x38f34b`: `DistributedCacheWritesDuration`
- `0x38f377`: `DistributedCacheWritesSize`
- `0x38f38d`: `DistributedCacheMisses`
- `0x38f3a3`: `DistributedCacheHits`
- `0x38f3b9`: `DistributedCacheFailures`
- `0x38f3cf`: `DistributedCachedObjectsRequested`

## pseudocode

```c

```

## disassembly

```asm
0x38f240  ldarg.0
0x38f241  ldarg.1
0x38f242  call     instance void Microsoft.SharePoint.Administration.SPUsageEntry::GetBaseObjectData(class Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo info)
0x38f247  ldarg.1
0x38f248  ldstr    aRequestcount// "RequestCount"
0x38f24d  ldarg.0
0x38f24e  ldfld    int16 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Requests
0x38f253  box      [mscorlib]System.Int16
0x38f258  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f25d  ldarg.1
0x38f25e  ldstr    aQuerycount// "QueryCount"
0x38f263  ldarg.0
0x38f264  ldfld    int16 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Queries
0x38f269  box      [mscorlib]System.Int16
0x38f26e  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f273  ldarg.1
0x38f274  ldstr    aQuerydurations// "QueryDurationSum"
0x38f279  ldarg.0
0x38f27a  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_QueryDurationSum
0x38f27f  box      [mscorlib]System.Int64
0x38f284  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f289  ldarg.1
0x38f28a  ldstr    aServicecallcou// "ServiceCallCount"
0x38f28f  ldarg.0
0x38f290  ldfld    int16 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ServiceCalls
0x38f295  box      [mscorlib]System.Int16
0x38f29a  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f29f  ldarg.1
0x38f2a0  ldstr    aServicecalldur// "ServiceCallDurationSum"
0x38f2a5  ldarg.0
0x38f2a6  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ServiceCallDurationSum
0x38f2ab  box      [mscorlib]System.Int64
0x38f2b0  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f2b5  ldarg.1
0x38f2b6  ldstr    aDuration// "Duration"
0x38f2bb  ldarg.0
0x38f2bc  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Duration
0x38f2c1  box      [mscorlib]System.Int64
0x38f2c6  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f2cb  ldarg.1
0x38f2cc  ldstr    aTitle_0// "Title"
0x38f2d1  ldarg.0
0x38f2d2  ldfld    string Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_Title
0x38f2d7  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f2dc  ldarg.1
0x38f2dd  ldstr    aSqllogicalread// "SqlLogicalReads"
0x38f2e2  ldarg.0
0x38f2e3  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_SqlLogicalReads
0x38f2e8  box      [mscorlib]System.Int64
0x38f2ed  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f2f2  ldarg.1
0x38f2f3  ldstr    aCpumcycles// "CPUMCycles"
0x38f2f8  ldarg.0
0x38f2f9  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_CPUMCycles
0x38f2fe  box      [mscorlib]System.Int64
0x38f303  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f308  ldarg.1
0x38f309  ldstr    aDistributedcac_0// "DistributedCacheReads"
0x38f30e  ldarg.0
0x38f30f  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheReads
0x38f314  box      [mscorlib]System.Int64
0x38f319  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f31e  ldarg.1
0x38f31f  ldstr    aDistributedcac_1// "DistributedCacheReadsDuration"
0x38f324  ldarg.0
0x38f325  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheReadsDuration
0x38f32a  box      [mscorlib]System.Int64
0x38f32f  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f334  ldarg.1
0x38f335  ldstr    aDistributedcac_3// "DistributedCacheWrites"
0x38f33a  ldarg.0
0x38f33b  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheWrites
0x38f340  box      [mscorlib]System.Int64
0x38f345  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f34a  ldarg.1
0x38f34b  ldstr    aDistributedcac_4// "DistributedCacheWritesDuration"
0x38f350  ldarg.0
0x38f351  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheWritesDuration
0x38f356  box      [mscorlib]System.Int64
0x38f35b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f360  ldarg.1
0x38f361  ldstr    aDistributedcac_2// "DistributedCacheReadsSize"
0x38f366  ldarg.0
0x38f367  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheReadsSize
0x38f36c  box      [mscorlib]System.Int64
0x38f371  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f376  ldarg.1
0x38f377  ldstr    aDistributedcac_5// "DistributedCacheWritesSize"
0x38f37c  ldarg.0
0x38f37d  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheWritesSize
0x38f382  box      [mscorlib]System.Int64
0x38f387  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f38c  ldarg.1
0x38f38d  ldstr    aDistributedcac_6// "DistributedCacheMisses"
0x38f392  ldarg.0
0x38f393  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheMisses
0x38f398  box      [mscorlib]System.Int64
0x38f39d  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f3a2  ldarg.1
0x38f3a3  ldstr    aDistributedcac_7// "DistributedCacheHits"
0x38f3a8  ldarg.0
0x38f3a9  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheHits
0x38f3ae  box      [mscorlib]System.Int64
0x38f3b3  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f3b8  ldarg.1
0x38f3b9  ldstr    aDistributedcac_8// "DistributedCacheFailures"
0x38f3be  ldarg.0
0x38f3bf  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCacheFailures
0x38f3c4  box      [mscorlib]System.Int64
0x38f3c9  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f3ce  ldarg.1
0x38f3cf  ldstr    aDistributedcac_9// "DistributedCachedObjectsRequested"
0x38f3d4  ldarg.0
0x38f3d5  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_distributedCachedObjectsRequested
0x38f3da  box      [mscorlib]System.Int64
0x38f3df  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f3e4  ldarg.1
0x38f3e5  ldstr    aManagedmemoryb// "ManagedMemoryBytes"
0x38f3ea  ldarg.0
0x38f3eb  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ManagedMemoryBytes
0x38f3f0  box      valuetype [mscorlib]System.Nullable`1<int64>
0x38f3f5  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f3fa  ldarg.1
0x38f3fb  ldstr    aManagedmemoryb_0// "ManagedMemoryBytesLOH"
0x38f400  ldarg.0
0x38f401  ldfld    valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ManagedMemoryBytesLOH
0x38f406  box      valuetype [mscorlib]System.Nullable`1<int64>
0x38f40b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f410  ldarg.1
0x38f411  ldstr    aCpuduration_0// "CPUDuration"
0x38f416  ldarg.0
0x38f417  ldfld    int64 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_CPUDuration
0x38f41c  box      [mscorlib]System.Int64
0x38f421  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f426  ldarg.1
0x38f427  ldstr    aProcessname// "ProcessName"
0x38f42c  ldarg.0
0x38f42d  ldfld    string Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ProcessName
0x38f432  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f437  ldarg.1
0x38f438  ldstr    aProcessid// "ProcessId"
0x38f43d  ldarg.0
0x38f43e  ldfld    int32 Microsoft.SharePoint.Administration.SPTaskUsageEntry::m_ProcessId
0x38f443  box      [mscorlib]System.Int32
0x38f448  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38f44d  ret
```
