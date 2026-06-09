# Microsoft.SharePoint.Administration.SPTaskUsageDefinition::get_Columns

- ea: `0x38e9b0`
- end: `0x38eb76`
- name: `Microsoft.SharePoint.Administration.SPTaskUsageDefinition::get_Columns`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x378200`
- `0x378210`
- `0x38e9b0`

## string_xrefs

- `0x38e9f7`: `ServiceCallCount`
- `0x38ea09`: `ServiceCallDurationSum`
- `0x38eb58`: `ProcessId`
- `0x38ea42`: `SqlLogicalReads`
- `0x38ea64`: `DistributedCacheReads`
- `0x38ea75`: `DistributedCacheReadsDuration`
- `0x38ea86`: `DistributedCacheReadsSize`
- `0x38ea97`: `DistributedCacheWrites`
- `0x38eaa8`: `DistributedCacheWritesDuration`
- `0x38eab9`: `DistributedCacheWritesSize`
- `0x38eaca`: `DistributedCacheMisses`
- `0x38eadb`: `DistributedCacheHits`
- `0x38eaec`: `DistributedCacheFailures`
- `0x38eafd`: `DistributedCachedObjectsRequested`

## pseudocode

```c

```

## disassembly

```asm
0x38e9b0  ldarg.0
0x38e9b1  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition> Microsoft.SharePoint.Administration.SPTaskUsageDefinition::m_Columns
0x38e9b6  brtrue   loc_38EB6F
0x38e9bb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::.ctor()
0x38e9c0  stloc.0
0x38e9c1  ldloc.0
0x38e9c2  ldstr    aRequestcount// "RequestCount"
0x38e9c7  ldc.i4.s 0x10
0x38e9c9  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38e9ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38e9d3  ldloc.0
0x38e9d4  ldstr    aQuerycount// "QueryCount"
0x38e9d9  ldc.i4.s 0x10
0x38e9db  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38e9e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38e9e5  ldloc.0
0x38e9e6  ldstr    aQuerydurations// "QueryDurationSum"
0x38e9eb  ldc.i4.0
0x38e9ec  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38e9f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38e9f6  ldloc.0
0x38e9f7  ldstr    aServicecallcou// "ServiceCallCount"
0x38e9fc  ldc.i4.s 0x10
0x38e9fe  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea08  ldloc.0
0x38ea09  ldstr    aServicecalldur// "ServiceCallDurationSum"
0x38ea0e  ldc.i4.0
0x38ea0f  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea14  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea19  ldloc.0
0x38ea1a  ldstr    aDuration// "Duration"
0x38ea1f  ldc.i4.0
0x38ea20  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea2a  ldloc.0
0x38ea2b  ldstr    aTitle_0// "Title"
0x38ea30  ldc.i4.s 0xC
0x38ea32  ldc.i4   0x80
0x38ea37  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x38ea3c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea41  ldloc.0
0x38ea42  ldstr    aSqllogicalread// "SqlLogicalReads"
0x38ea47  ldc.i4.0
0x38ea48  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea52  ldloc.0
0x38ea53  ldstr    aCpumcycles// "CPUMCycles"
0x38ea58  ldc.i4.0
0x38ea59  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea63  ldloc.0
0x38ea64  ldstr    aDistributedcac_0// "DistributedCacheReads"
0x38ea69  ldc.i4.0
0x38ea6a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea74  ldloc.0
0x38ea75  ldstr    aDistributedcac_1// "DistributedCacheReadsDuration"
0x38ea7a  ldc.i4.0
0x38ea7b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea85  ldloc.0
0x38ea86  ldstr    aDistributedcac_2// "DistributedCacheReadsSize"
0x38ea8b  ldc.i4.0
0x38ea8c  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ea91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ea96  ldloc.0
0x38ea97  ldstr    aDistributedcac_3// "DistributedCacheWrites"
0x38ea9c  ldc.i4.0
0x38ea9d  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eaa2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eaa7  ldloc.0
0x38eaa8  ldstr    aDistributedcac_4// "DistributedCacheWritesDuration"
0x38eaad  ldc.i4.0
0x38eaae  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eab3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eab8  ldloc.0
0x38eab9  ldstr    aDistributedcac_5// "DistributedCacheWritesSize"
0x38eabe  ldc.i4.0
0x38eabf  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eac4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eac9  ldloc.0
0x38eaca  ldstr    aDistributedcac_6// "DistributedCacheMisses"
0x38eacf  ldc.i4.0
0x38ead0  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ead5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eada  ldloc.0
0x38eadb  ldstr    aDistributedcac_7// "DistributedCacheHits"
0x38eae0  ldc.i4.0
0x38eae1  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eae6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eaeb  ldloc.0
0x38eaec  ldstr    aDistributedcac_8// "DistributedCacheFailures"
0x38eaf1  ldc.i4.0
0x38eaf2  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eaf7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eafc  ldloc.0
0x38eafd  ldstr    aDistributedcac_9// "DistributedCachedObjectsRequested"
0x38eb02  ldc.i4.0
0x38eb03  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eb08  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eb0d  ldloc.0
0x38eb0e  ldstr    aManagedmemoryb// "ManagedMemoryBytes"
0x38eb13  ldc.i4.0
0x38eb14  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eb19  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eb1e  ldloc.0
0x38eb1f  ldstr    aManagedmemoryb_0// "ManagedMemoryBytesLOH"
0x38eb24  ldc.i4.0
0x38eb25  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eb2a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eb2f  ldloc.0
0x38eb30  ldstr    aCpuduration_0// "CPUDuration"
0x38eb35  ldc.i4.0
0x38eb36  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eb3b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eb40  ldloc.0
0x38eb41  ldstr    aProcessname// "ProcessName"
0x38eb46  ldc.i4.s 0xC
0x38eb48  ldc.i4   0x80
0x38eb4d  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x38eb52  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eb57  ldloc.0
0x38eb58  ldstr    aProcessid// "ProcessId"
0x38eb5d  ldc.i4.8
0x38eb5e  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38eb63  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38eb68  ldarg.0
0x38eb69  ldloc.0
0x38eb6a  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition> Microsoft.SharePoint.Administration.SPTaskUsageDefinition::m_Columns
0x38eb6f  ldarg.0
0x38eb70  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition> Microsoft.SharePoint.Administration.SPTaskUsageDefinition::m_Columns
0x38eb75  ret
```
