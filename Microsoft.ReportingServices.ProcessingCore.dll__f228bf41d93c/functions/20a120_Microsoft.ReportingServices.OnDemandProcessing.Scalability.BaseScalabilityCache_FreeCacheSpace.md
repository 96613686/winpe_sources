# Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::FreeCacheSpace

- ea: `0x20a120`
- end: `0x20a453`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::FreeCacheSpace`
- size: `819`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x205060`
- `0x20a060`
- `0x20af20`

## callees

- `0x209e10`
- `0x209e20`
- `0x20a0a0`
- `0x20a100`
- `0x20a120`
- `0x20a480`

## string_xrefs

- `0x20a22d`: `ScalabilityCache {0}|{1} expanding cache. ExpansionKB: {2} TotalAllocation: {3} CacheSizeKB: {4} CacheCapacityKB: {5}`
- `0x20a2d0`: `ScalabilityCache {0}|{1} responding to pressure.  PendingNotifications: {2} CacheSizeKB: {3} CacheCapacityKB: {4}`
- `0x20a3c5`: `ScalabilityCache {0}|{1} done responding to pressure.  Freed: {2} KB. Speed: {3:F2} KB/Sec.  CacheSizeKB {4} CacheCapacityKB {5}`

## pseudocode

```c

```

## disassembly

```asm
0x20a120  ldarg.0
0x20a121  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_freeingSpace
0x20a126  brtrue.s loc_20A130
0x20a128  ldarg.0
0x20a129  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inStreamOper
0x20a12e  brfalse.s loc_20A131
0x20a130  ret
0x20a131  ldc.i4.0
0x20a132  stloc.0
0x20a133  ldarg.0
0x20a134  ldc.i4.1
0x20a135  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inStreamOper
0x20a13a  ldarg.0
0x20a13b  ldc.i4.1
0x20a13c  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_freeingSpace
0x20a141  ldarg.0
0x20a142  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x20a147  call     int64 [mscorlib]System.Threading.Interlocked::Read(int64&)
0x20a14c  stloc.1
0x20a14d  ldloc.1
0x20a14e  ldc.i4.0
0x20a14f  conv.i8
0x20a150  bgt.s    loc_20A157
0x20a152  leave    loc_20A452
0x20a157  ldarg.0
0x20a158  ldflda   int32 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_pendingNotificationCount
0x20a15d  ldc.i4.0
0x20a15e  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0x20a163  stloc.0
0x20a164  ldarg.0
0x20a165  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_pendingFreeBytes
0x20a16a  ldc.i4.0
0x20a16b  conv.i8
0x20a16c  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x20a171  pop
0x20a172  ldarg.2
0x20a173  ldarg.1
0x20a174  conv.i8
0x20a175  add
0x20a176  ldloc.1
0x20a177  sub
0x20a178  stloc.2
0x20a179  ldloc.2
0x20a17a  ldc.i4.0
0x20a17b  conv.i8
0x20a17c  bgt.s    loc_20A183
0x20a17e  leave    loc_20A452
0x20a183  ldloc.0
0x20a184  brtrue   loc_20A2B8
0x20a189  ldarg.0
0x20a18a  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheLifetimeTimer
0x20a18f  brfalse  loc_20A2B8
0x20a194  ldarg.0
0x20a195  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheLifetimeTimer
0x20a19a  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x20a19f  ldarg.0
0x20a1a0  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_expansionIntervalMs
0x20a1a5  sub
0x20a1a6  ldarg.0
0x20a1a7  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_lastExpansionOrNotificationMs
0x20a1ac  ble      loc_20A2B8
0x20a1b1  ldarg.0
0x20a1b2  call     instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::ResetExpansionOrNotificationInterval()
0x20a1b7  ldarg.0
0x20a1b8  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalAuditedBytes
0x20a1bd  ldloc.1
0x20a1be  sub
0x20a1bf  conv.r8
0x20a1c0  ldarg.0
0x20a1c1  ldfld    float64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheExpansionRatio
0x20a1c6  mul
0x20a1c7  conv.i8
0x20a1c8  stloc.s  5
0x20a1ca  ldloc.s  5
0x20a1cc  ldsfld   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::CacheExpansionMaxBytes
0x20a1d1  ble.s    loc_20A1DC
0x20a1d3  ldsfld   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::CacheExpansionMaxBytes
0x20a1d8  stloc.s  5
0x20a1da  br.s     loc_20A201
0x20a1dc  ldloc.s  5
0x20a1de  ldc.i4   0x100000
0x20a1e3  conv.i8
0x20a1e4  bge.s    loc_20A201
0x20a1e6  ldc.i4   0x100000
0x20a1eb  conv.i8
0x20a1ec  stloc.s  5
0x20a1ee  ldarg.0
0x20a1ef  ldarg.0
0x20a1f0  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalAuditedBytes
0x20a1f5  ldc.i4   0x100000
0x20a1fa  conv.i8
0x20a1fb  add
0x20a1fc  stfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalAuditedBytes
0x20a201  ldloc.s  5
0x20a203  ldc.i4.0
0x20a204  conv.i8
0x20a205  ble      loc_20A2B8
0x20a20a  ldarg.0
0x20a20b  ldflda   int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x20a210  ldloc.s  5
0x20a212  call     int64 [mscorlib]System.Threading.Interlocked::Add(int64&, int64)
0x20a217  stloc.1
0x20a218  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a21d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x20a222  brfalse  loc_20A2A9
0x20a227  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a22c  ldc.i4.4
0x20a22d  ldstr    aScalabilitycac_0// "ScalabilityCache {0}|{1} expanding cach"...
0x20a232  ldc.i4.6
0x20a233  newarr   [mscorlib]System.Object
0x20a238  dup
0x20a239  ldc.i4.0
0x20a23a  ldarg.0
0x20a23b  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x20a240  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType
0x20a245  stelem.ref
0x20a246  dup
0x20a247  ldc.i4.1
0x20a248  ldarg.0
0x20a249  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_CacheType()
0x20a24e  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType
0x20a253  stelem.ref
0x20a254  dup
0x20a255  ldc.i4.2
0x20a256  ldloc.s  5
0x20a258  ldc.i4   0x400
0x20a25d  conv.i8
0x20a25e  div
0x20a25f  box      [mscorlib]System.Int64
0x20a264  stelem.ref
0x20a265  dup
0x20a266  ldc.i4.3
0x20a267  ldarg.0
0x20a268  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalAuditedBytes
0x20a26d  ldc.i4   0x400
0x20a272  conv.i8
0x20a273  div
0x20a274  box      [mscorlib]System.Int64
0x20a279  stelem.ref
0x20a27a  dup
0x20a27b  ldc.i4.4
0x20a27c  ldarg.0
0x20a27d  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheSizeBytes
0x20a282  ldc.i4   0x400
0x20a287  conv.i8
0x20a288  div
0x20a289  box      [mscorlib]System.Int64
0x20a28e  stelem.ref
0x20a28f  dup
0x20a290  ldc.i4.5
0x20a291  ldarg.0
0x20a292  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x20a297  ldc.i4   0x400
0x20a29c  conv.i8
0x20a29d  div
0x20a29e  box      [mscorlib]System.Int64
0x20a2a3  stelem.ref
0x20a2a4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x20a2a9  ldloc.2
0x20a2aa  ldloc.s  5
0x20a2ac  sub
0x20a2ad  stloc.2
0x20a2ae  ldloc.2
0x20a2af  ldc.i4.0
0x20a2b0  conv.i8
0x20a2b1  bgt.s    loc_20A2B8
0x20a2b3  leave    loc_20A452
0x20a2b8  ldnull
0x20a2b9  stloc.3
0x20a2ba  ldloc.0
0x20a2bb  ldc.i4.0
0x20a2bc  ble.s    loc_20A33B
0x20a2be  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a2c3  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x20a2c8  brfalse.s loc_20A33B
0x20a2ca  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a2cf  ldc.i4.4
0x20a2d0  ldstr    aScalabilitycac_1// "ScalabilityCache {0}|{1} responding to "...
0x20a2d5  ldc.i4.5
0x20a2d6  newarr   [mscorlib]System.Object
0x20a2db  dup
0x20a2dc  ldc.i4.0
0x20a2dd  ldarg.0
0x20a2de  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x20a2e3  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType
0x20a2e8  stelem.ref
0x20a2e9  dup
0x20a2ea  ldc.i4.1
0x20a2eb  ldarg.0
0x20a2ec  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_CacheType()
0x20a2f1  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType
0x20a2f6  stelem.ref
0x20a2f7  dup
0x20a2f8  ldc.i4.2
0x20a2f9  ldloc.0
0x20a2fa  box      [mscorlib]System.Int32
0x20a2ff  stelem.ref
0x20a300  dup
0x20a301  ldc.i4.3
0x20a302  ldarg.0
0x20a303  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheSizeBytes
0x20a308  ldc.i4   0x400
0x20a30d  conv.i8
0x20a30e  div
0x20a30f  box      [mscorlib]System.Int64
0x20a314  stelem.ref
0x20a315  dup
0x20a316  ldc.i4.4
0x20a317  ldarg.0
0x20a318  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheCapacityBytes
0x20a31d  ldc.i4   0x400
0x20a322  conv.i8
0x20a323  div
0x20a324  box      [mscorlib]System.Int64
0x20a329  stelem.ref
0x20a32a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x20a32f  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x20a334  stloc.3
0x20a335  ldloc.3
0x20a336  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x20a33b  ldarg.0
0x20a33c  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_serializationTimer
0x20a341  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x20a346  ldarg.0
0x20a347  ldloc.2
0x20a348  stfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inProgressFreeBytes
0x20a34d  ldarg.0
0x20a34e  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::FulfillInProgressFree()
0x20a353  ldarg.0
0x20a354  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_serializationTimer
0x20a359  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x20a35e  ldloc.2
0x20a35f  ldarg.0
0x20a360  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_inProgressFreeBytes
0x20a365  sub
0x20a366  stloc.s  4
0x20a368  ldarg.0
0x20a369  ldarg.0
0x20a36a  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalBytesSerialized
0x20a36f  ldloc.s  4
0x20a371  add
0x20a372  stfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_totalBytesSerialized
0x20a377  ldarg.0
0x20a378  call     instance void Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::UpdatePeakCacheSize()
0x20a37d  ldloc.0
0x20a37e  ldc.i4.0
0x20a37f  ble      loc_20A42F
0x20a384  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a389  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x20a38e  brfalse  loc_20A42F
0x20a393  ldloc.3
0x20a394  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x20a399  ldloc.3
0x20a39a  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x20a39f  conv.r8
0x20a3a0  ldc.r8   1000.0
0x20a3a9  div
0x20a3aa  stloc.s  6
0x20a3ac  ldloc.s  4
0x20a3ae  ldc.i4   0x400
0x20a3b3  conv.i8
0x20a3b4  div
0x20a3b5  stloc.s  7
0x20a3b7  ldloc.s  7
0x20a3b9  conv.r8
0x20a3ba  ldloc.s  6
0x20a3bc  div
0x20a3bd  stloc.s  8
0x20a3bf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20a3c4  ldc.i4.4
0x20a3c5  ldstr    aScalabilitycac_2// "ScalabilityCache {0}|{1} done respondin"...
0x20a3ca  ldc.i4.6
0x20a3cb  newarr   [mscorlib]System.Object
0x20a3d0  dup
0x20a3d1  ldc.i4.0
0x20a3d2  ldarg.0
0x20a3d3  call     instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_OwnerComponent()
0x20a3d8  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ComponentType
0x20a3dd  stelem.ref
0x20a3de  dup
0x20a3df  ldc.i4.1
0x20a3e0  ldarg.0
0x20a3e1  callvirt instance valuetype Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::get_CacheType()
0x20a3e6  box      Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalabilityCacheType
0x20a3eb  stelem.ref
0x20a3ec  dup
0x20a3ed  ldc.i4.2
0x20a3ee  ldloc.s  7
0x20a3f0  box      [mscorlib]System.Int64
0x20a3f5  stelem.ref
0x20a3f6  dup
0x20a3f7  ldc.i4.3
0x20a3f8  ldloc.s  8
0x20a3fa  box      [mscorlib]System.Double
0x20a3ff  stelem.ref
0x20a400  dup
0x20a401  ldc.i4.4
0x20a402  ldarg.0
0x20a403  ldfld    int64 Microsoft.ReportingServices.OnDemandProcessing.Scalability.BaseScalabilityCache::m_cacheSizeBytes
0x20a408  ldc.i4   0x400
  ... truncated ...
```
