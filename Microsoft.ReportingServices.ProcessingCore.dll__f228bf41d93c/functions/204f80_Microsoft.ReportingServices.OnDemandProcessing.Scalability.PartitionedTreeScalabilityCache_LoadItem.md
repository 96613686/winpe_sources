# Microsoft.ReportingServices.OnDemandProcessing.Scalability.PartitionedTreeScalabilityCache::LoadItem

- ea: `0x204f80`
- end: `0x205056`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.PartitionedTreeScalabilityCache::LoadItem`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x204d80`

## callees

- `0x2012c0`
- `0x204f80`
- `0x205060`
- `0x205c90`
- `0x207110`
- `0x207530`
- `0x207550`
- `0x207590`
- `0x20b770`

## string_xrefs

- `0x204f8e`: `PartitionedTreeScalabilityCache should not Load during serialization`

## pseudocode

```c

```

## disassembly

```asm
0x204f80  ldarg.0
0x204f81  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inStreamOper
0x204f86  brfalse.s loc_204F98
0x204f88  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x204f8d  ldc.i4.0
0x204f8e  ldstr    aPartitionedtre_1// "PartitionedTreeScalabilityCache should "...
0x204f93  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x204f98  ldnull
0x204f99  stloc.0
0x204f9a  ldarg.0
0x204f9b  ldc.i4.1
0x204f9c  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inStreamOper
0x204fa1  ldarg.0
0x204fa2  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_deserializationTimer
0x204fa7  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x204fac  ldarg.1
0x204fad  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::get_Id()
0x204fb2  stloc.1
0x204fb3  ldloca.s 1
0x204fb5  call     instance bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID::get_IsTemporary()
0x204fba  brtrue.s loc_204FDC
0x204fbc  ldloca.s 1
0x204fbe  call     instance bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID::get_HasMultiPart()
0x204fc3  brfalse.s loc_204FDC
0x204fc5  ldarg.0
0x204fc6  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.TreePartitionManager Microsoft.ReportingServices.OnDemandProcessing.Scalability.PartitionedTreeScalabilityCache::m_partitionManager
0x204fcb  ldloc.1
0x204fcc  callvirt instance int64 Microsoft.ReportingServices.OnDemandProcessing.TreePartitionManager::GetTreePartitionOffset(valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID id)
0x204fd1  stloc.2
0x204fd2  ldloc.2
0x204fd3  ldc.i4.0
0x204fd4  conv.i8
0x204fd5  bge.s    loc_204FEC
0x204fd7  ldnull
0x204fd8  stloc.s  4
0x204fda  leave.s  loc_205053
0x204fdc  ldarg.1
0x204fdd  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference::get_Id()
0x204fe2  stloc.s  5
0x204fe4  ldloca.s 5
0x204fe6  call     instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID::get_Value()
0x204feb  stloc.2
0x204fec  ldloc.2
0x204fed  ldc.i4.0
0x204fee  conv.i8
0x204fef  bge.s    loc_205019
0x204ff1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x204ff6  ldc.i4.0
0x204ff7  ldstr    aInvalidOffsetF_0// "Invalid offset for item.  ReferenceID: "...
0x204ffc  ldc.i4.2
0x204ffd  newarr   [mscorlib]System.Object
0x205002  dup
0x205003  ldc.i4.0
0x205004  ldloc.1
0x205005  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ReferenceID
0x20500a  stelem.ref
0x20500b  dup
0x20500c  ldc.i4.1
0x20500d  ldloc.2
0x20500e  box      [mscorlib]System.Int64
0x205013  stelem.ref
0x205014  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x205019  ldarg.0
0x20501a  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_storage
0x20501f  ldloc.2
0x205020  ldloca.s 3
0x205022  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage::Retrieve(int64 offset, [out] int64& persistedSize)
0x205027  castclass Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorable
0x20502c  stloc.0
0x20502d  leave.s  loc_205042
0x20502f  ldarg.0
0x205030  ldc.i4.0
0x205031  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inStreamOper
0x205036  ldarg.0
0x205037  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_deserializationTimer
0x20503c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x205041  endfinally
0x205042  ldarg.0
0x205043  ldarg.1
0x205044  ldloc.0
0x205045  ldc.i4.1
0x205046  ldloc.0
0x205047  call     int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.ItemSizes::SizeOf(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorable obj)
0x20504c  call     instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.PartitionedTreeScalabilityCache::CacheItem(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseReference reference, class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorable item, bool fromDeserialize, int32 newItemSize)
0x205051  ldloc.0
0x205052  ret
0x205053  ldloc.s  4
0x205055  ret
```
