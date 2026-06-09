# Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::Dispose

- ea: `0x209e90`
- end: `0x209fd8`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::Dispose`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x204d10`
- `0x20a8e0`

## callees

- `0x209e10`
- `0x209e20`
- `0x209e30`
- `0x209e90`
- `0x20b7d0`
- `0x20b7f0`

## string_xrefs

- `0x209ef5`: `ScalabilityCache {0}|{1} Done. `
- `0x209f2b`: `AvgSpeed {0:F2} KB/s. StreamSize {1} MB. `

## pseudocode

```c

```

## disassembly

```asm
0x209e90  ldarg.0
0x209e91  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_disposed
0x209e96  brfalse.s loc_209E9D
0x209e98  leave    loc_209FD7
0x209e9d  ldarg.0
0x209e9e  ldc.i4.1
0x209e9f  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_disposed
0x209ea4  ldarg.0
0x209ea5  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_serializationTimer
0x209eaa  brfalse  loc_209F96
0x209eaf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x209eb4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x209eb9  brfalse  loc_209F96
0x209ebe  ldc.i4.m1
0x209ebf  conv.i8
0x209ec0  stloc.0
0x209ec1  ldarg.0
0x209ec2  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_storage
0x209ec7  brfalse.s loc_209ED5
0x209ec9  ldarg.0
0x209eca  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_storage
0x209ecf  callvirt instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage::get_StreamSize()
0x209ed4  stloc.0
0x209ed5  ldarg.0
0x209ed6  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalBytesSerialized
0x209edb  ldc.i4   0x400
0x209ee0  conv.i8
0x209ee1  div
0x209ee2  stloc.1
0x209ee3  ldarg.0
0x209ee4  call     instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_SerializationDurationMs()
0x209ee9  conv.r8
0x209eea  ldc.r8   1000.0
0x209ef3  div
0x209ef4  stloc.2
0x209ef5  ldstr    aScalabilitycac// "ScalabilityCache {0}|{1} Done. "
0x209efa  ldarg.0
0x209efb  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x209f00  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType
0x209f05  ldarg.0
0x209f06  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_CacheType()
0x209f0b  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType
0x209f10  call     string [mscorlib]System.String::Format(string, object, object)
0x209f15  ldstr    aAuditedheapser// "AuditedHeapSerialized: {0} KB. Serializ"...
0x209f1a  ldloc.1
0x209f1b  box      [mscorlib]System.Int64
0x209f20  ldloc.2
0x209f21  box      [mscorlib]System.Double
0x209f26  call     string [mscorlib]System.String::Format(string, object, object)
0x209f2b  ldstr    aAvgspeed0F2KbS// "AvgSpeed {0:F2} KB/s. StreamSize {1} MB"...
0x209f30  ldloc.1
0x209f31  conv.r8
0x209f32  ldloc.2
0x209f33  div
0x209f34  box      [mscorlib]System.Double
0x209f39  ldloc.0
0x209f3a  ldc.i4   0x100000
0x209f3f  conv.i8
0x209f40  div
0x209f41  box      [mscorlib]System.Int64
0x209f46  call     string [mscorlib]System.String::Format(string, object, object)
0x209f4b  ldstr    aFinalauditedhe// "FinalAuditedHeapSize {0} KB. LifetimeFr"...
0x209f50  ldarg.0
0x209f51  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalAuditedBytes
0x209f56  ldc.i4   0x400
0x209f5b  conv.i8
0x209f5c  div
0x209f5d  box      [mscorlib]System.Int64
0x209f62  ldarg.0
0x209f63  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalFreedBytes
0x209f68  ldc.i4   0x400
0x209f6d  conv.i8
0x209f6e  div
0x209f6f  box      [mscorlib]System.Int64
0x209f74  call     string [mscorlib]System.String::Format(string, object, object)
0x209f79  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x209f7e  stloc.3
0x209f7f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x209f84  ldc.i4.4
0x209f85  ldloc.3
0x209f86  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x209f8b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x209f90  ldloc.3
0x209f91  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x209f96  ldarg.0
0x209f97  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_storage
0x209f9c  brfalse.s loc_209FB0
0x209f9e  ldarg.0
0x209f9f  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_storage
0x209fa4  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage::Close()
0x209fa9  ldarg.0
0x209faa  ldnull
0x209fab  stfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IStorage Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_storage
0x209fb0  ldarg.0
0x209fb1  ldnull
0x209fb2  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_serializationTimer
0x209fb7  ldarg.0
0x209fb8  ldnull
0x209fb9  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_deserializationTimer
0x209fbe  leave.s  loc_209FD7
0x209fc0  ldarg.0
0x209fc1  ldc.i4.0
0x209fc2  conv.i8
0x209fc3  stfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheSizeBytes
0x209fc8  ldarg.0
0x209fc9  ldc.i4.0
0x209fca  conv.i8
0x209fcb  stfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x209fd0  ldarg.0
0x209fd1  call     instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::Dispose()
0x209fd6  endfinally
0x209fd7  ret
```
