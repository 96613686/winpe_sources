# Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::SetNewMemoryTarget

- ea: `0x20a510`
- end: `0x20a6d9`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::SetNewMemoryTarget`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x209e10`
- `0x209e20`
- `0x20a080`
- `0x20a510`

## string_xrefs

- `0x20a544`: `ScalabilityCache.SetNewMemoryTarget: CacheType: {0}|{1} NewTargetKB: {2} CacheSizeKB: {3} CacheCapacityKB: {4} CurrentFreeableKB: {5} CurrentUsageKB: {6}`
- `0x20a5c4`: `ScalabilityCache.SetNewMemoryTarget: CacheType: {0}|{1} `
- `0x20a5e4`: `NewTargetKB: {0} CacheSizeKB: {1} `
- `0x20a60b`: `CacheCapacityKB: {0} CurrentFreeableKB: {1} CurrentUsageKB: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x20a510  ldarg.0
0x20a511  call     instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_MinReservedMemoryKB()
0x20a516  stloc.0
0x20a517  ldarg.1
0x20a518  ldloc.0
0x20a519  bge.s    loc_20A523
0x20a51b  ldarg.0
0x20a51c  call     instance int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_MinReservedMemoryKB()
0x20a521  starg.s  1
0x20a523  ldarg.0
0x20a524  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x20a529  call     int64 [mscorlib]System.Threading.Interlocked::Read(int64&)
0x20a52e  stloc.1
0x20a52f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a534  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x20a539  brfalse  loc_20A5BF
0x20a53e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a543  ldc.i4.4
0x20a544  ldstr    aScalabilitycac_3// "ScalabilityCache.SetNewMemoryTarget: Ca"...
0x20a549  ldc.i4.7
0x20a54a  newarr   [mscorlib]System.Object
0x20a54f  dup
0x20a550  ldc.i4.0
0x20a551  ldarg.0
0x20a552  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x20a557  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType
0x20a55c  stelem.ref
0x20a55d  dup
0x20a55e  ldc.i4.1
0x20a55f  ldarg.0
0x20a560  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_CacheType()
0x20a565  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType
0x20a56a  stelem.ref
0x20a56b  dup
0x20a56c  ldc.i4.2
0x20a56d  ldarg.1
0x20a56e  box      [mscorlib]System.Int64
0x20a573  stelem.ref
0x20a574  dup
0x20a575  ldc.i4.3
0x20a576  ldarg.0
0x20a577  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheSizeBytes
0x20a57c  call     int64 [mscorlib]System.Threading.Interlocked::Read(int64&)
0x20a581  ldc.i4   0x400
0x20a586  conv.i8
0x20a587  div
0x20a588  box      [mscorlib]System.Int64
0x20a58d  stelem.ref
0x20a58e  dup
0x20a58f  ldc.i4.4
0x20a590  ldloc.1
0x20a591  ldc.i4   0x400
0x20a596  conv.i8
0x20a597  div
0x20a598  box      [mscorlib]System.Int64
0x20a59d  stelem.ref
0x20a59e  dup
0x20a59f  ldc.i4.5
0x20a5a0  ldarg.0
0x20a5a1  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentFreeableMemoryKBytes()
0x20a5a6  box      [mscorlib]System.Int64
0x20a5ab  stelem.ref
0x20a5ac  dup
0x20a5ad  ldc.i4.6
0x20a5ae  ldarg.0
0x20a5af  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentMemoryUsageKBytes()
0x20a5b4  box      [mscorlib]System.Int64
0x20a5b9  stelem.ref
0x20a5ba  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x20a5bf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x20a5c4  ldstr    aScalabilitycac_4// "ScalabilityCache.SetNewMemoryTarget: Ca"...
0x20a5c9  ldarg.0
0x20a5ca  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x20a5cf  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType
0x20a5d4  ldarg.0
0x20a5d5  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_CacheType()
0x20a5da  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType
0x20a5df  call     string [mscorlib]System.String::Format(string, object, object)
0x20a5e4  ldstr    aNewtargetkb0Ca// "NewTargetKB: {0} CacheSizeKB: {1} "
0x20a5e9  ldarg.1
0x20a5ea  box      [mscorlib]System.Int64
0x20a5ef  ldarg.0
0x20a5f0  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheSizeBytes
0x20a5f5  call     int64 [mscorlib]System.Threading.Interlocked::Read(int64&)
0x20a5fa  ldc.i4   0x400
0x20a5ff  conv.i8
0x20a600  div
0x20a601  box      [mscorlib]System.Int64
0x20a606  call     string [mscorlib]System.String::Format(string, object, object)
0x20a60b  ldstr    aCachecapacityk// "CacheCapacityKB: {0} CurrentFreeableKB:"...
0x20a610  ldloc.1
0x20a611  ldc.i4   0x400
0x20a616  conv.i8
0x20a617  div
0x20a618  box      [mscorlib]System.Int64
0x20a61d  ldarg.0
0x20a61e  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentFreeableMemoryKBytes()
0x20a623  box      [mscorlib]System.Int64
0x20a628  ldarg.0
0x20a629  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentMemoryUsageKBytes()
0x20a62e  box      [mscorlib]System.Int64
0x20a633  call     string [mscorlib]System.String::Format(string, object, object, object)
0x20a638  call     string [mscorlib]System.String::Concat(string, string, string)
0x20a63d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x20a642  ldarg.0
0x20a643  ldflda   int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_pendingNotificationCount
0x20a648  ldc.i4.1
0x20a649  call     int32 [mscorlib]System.Threading.Interlocked::Add(int32&, int32)
0x20a64e  pop
0x20a64f  ldarg.1
0x20a650  ldc.i4   0x400
0x20a655  conv.i8
0x20a656  mul
0x20a657  stloc.2
0x20a658  ldarg.0
0x20a659  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x20a65e  ldloc.2
0x20a65f  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x20a664  pop
0x20a665  ldloc.1
0x20a666  ldloc.2
0x20a667  sub
0x20a668  stloc.3
0x20a669  ldloc.3
0x20a66a  ldc.i4.0
0x20a66b  conv.i8
0x20a66c  bge.s    loc_20A671
0x20a66e  ldc.i4.0
0x20a66f  conv.i8
0x20a670  stloc.3
0x20a671  ldarg.0
0x20a672  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_pendingFreeBytes
0x20a677  ldloc.3
0x20a678  call     int64 [mscorlib]System.Threading.Interlocked::Add(int64&, int64)
0x20a67d  pop
0x20a67e  ldarg.0
0x20a67f  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_receivedShrinkRequest
0x20a684  brtrue.s loc_20A6D8
0x20a686  ldloc.3
0x20a687  ldc.i4.0
0x20a688  conv.i8
0x20a689  ble.s    loc_20A6D8
0x20a68b  ldarg.0
0x20a68c  ldc.i4.1
0x20a68d  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_receivedShrinkRequest
0x20a692  ldarg.0
0x20a693  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x20a698  stloc.s  4
0x20a69a  ldloc.s  4
0x20a69c  ldc.i4.1
0x20a69d  beq.s    loc_20A6A6
0x20a69f  ldloc.s  4
0x20a6a1  ldc.i4.2
0x20a6a2  beq.s    loc_20A6B7
0x20a6a4  br.s     loc_20A6C8
0x20a6a6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x20a6ab  ldc.i4.2
0x20a6ac  ldstr    aPaginationScal// "Pagination Scalability -- Memory Shrink"...
0x20a6b1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x20a6b6  ret
0x20a6b7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ExcelRendererTracer()
0x20a6bc  ldc.i4.2
0x20a6bd  ldstr    aRenderingScala// "Rendering Scalability -- Memory Shrink "...
0x20a6c2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x20a6c7  ret
0x20a6c8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a6cd  ldc.i4.2
0x20a6ce  ldstr    aProcessingScal// "Processing Scalability -- Memory Shrink"...
0x20a6d3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x20a6d8  ret
```
