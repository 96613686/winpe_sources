# Microsoft.ReportingServices.Library.RenderFromSnapshot::TryHitLocalCache

- ea: `0x2b370`
- end: `0x2b440`
- name: `Microsoft.ReportingServices.Library.RenderFromSnapshot::TryHitLocalCache`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x28bb0`
- `0x297a0`
- `0x297b0`
- `0x29810`
- `0x2a840`
- `0x2ab40`
- `0x2b370`
- `0x2c690`
- `0x55800`
- `0x55810`
- `0x55880`
- `0x5b880`
- `0x609c0`

## string_xrefs

- `0x2b39f`: `Using cached result`
- `0x2b434`: `Could not find cached result`

## pseudocode

```c

```

## disassembly

```asm
0x2b370  ldarg.0
0x2b371  call     instance class Microsoft.ReportingServices.Library.SnapshotManager Microsoft.ReportingServices.Library.RenderStrategyBase::get_SnapshotManager()
0x2b376  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.SnapshotManager::get_ChunkTargetSnapshot()
0x2b37b  stloc.0
0x2b37c  ldsfld   class Microsoft.ReportingServices.Library.RSLocalCacheManager Microsoft.ReportingServices.Library.RSLocalCacheManager::Current
0x2b381  ldarg.0
0x2b382  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2b387  callvirt instance class Microsoft.ReportingServices.Library.ExecutionParameters Microsoft.ReportingServices.Library.ReportExecutionBase::get_RequestInfo()
0x2b38c  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.ExecutionParameters::ReportContext
0x2b391  ldnull
0x2b392  ldloc.0
0x2b393  callvirt instance class Microsoft.ReportingServices.Library.ReportRenderingResult Microsoft.ReportingServices.Library.RSLocalCacheManager::GetCachedResult(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext context, string streamName, class Microsoft.ReportingServices.Library.ReportSnapshot reportSnapshot)
0x2b398  stloc.1
0x2b399  ldloc.1
0x2b39a  brfalse  loc_2B434
0x2b39f  ldstr    aUsingCachedRes// "Using cached result"
0x2b3a4  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x2b3a9  ldarg.0
0x2b3aa  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2b3af  callvirt instance class Microsoft.ReportingServices.Library.IExecutionDataProvider Microsoft.ReportingServices.Library.ReportExecutionBase::get_DataProvider()
0x2b3b4  callvirt instance class Microsoft.ReportingServices.Library.StreamManager Microsoft.ReportingServices.Library.IExecutionDataProvider::get_StreamManager()
0x2b3b9  stloc.2
0x2b3ba  ldloc.2
0x2b3bb  ldloc.1
0x2b3bc  ldfld    class Microsoft.ReportingServices.Library.RSStream Microsoft.ReportingServices.Library.ReportRenderingResult::Stream
0x2b3c1  callvirt instance void Microsoft.ReportingServices.Library.StreamManager::SetPrimaryStream(class Microsoft.ReportingServices.Library.RSStream stream)
0x2b3c6  ldloc.2
0x2b3c7  ldloc.1
0x2b3c8  ldfld    string[] Microsoft.ReportingServices.Library.ReportRenderingResult::SecondaryStreamNames
0x2b3cd  callvirt instance void Microsoft.ReportingServices.Library.StreamManager::SetSecondaryStreamNames(string[] streamNames)
0x2b3d2  ldloc.1
0x2b3d3  ldfld    string[] Microsoft.ReportingServices.Library.ReportRenderingResult::SecondaryCacheableStreamNames
0x2b3d8  stloc.3
0x2b3d9  ldc.i4.0
0x2b3da  stloc.s  4
0x2b3dc  br.s     loc_2B41A
0x2b3de  ldloc.3
0x2b3df  ldloc.s  4
0x2b3e1  ldelem.ref
0x2b3e2  stloc.s  5
0x2b3e4  ldsfld   class Microsoft.ReportingServices.Library.RSLocalCacheManager Microsoft.ReportingServices.Library.RSLocalCacheManager::Current
0x2b3e9  ldarg.0
0x2b3ea  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2b3ef  callvirt instance class Microsoft.ReportingServices.Library.ExecutionParameters Microsoft.ReportingServices.Library.ReportExecutionBase::get_RequestInfo()
0x2b3f4  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.ExecutionParameters::ReportContext
0x2b3f9  ldloc.s  5
0x2b3fb  ldloc.0
0x2b3fc  callvirt instance class Microsoft.ReportingServices.Library.ReportRenderingResult Microsoft.ReportingServices.Library.RSLocalCacheManager::GetCachedResult(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext context, string streamName, class Microsoft.ReportingServices.Library.ReportSnapshot reportSnapshot)
0x2b401  stloc.s  6
0x2b403  ldloc.s  6
0x2b405  brfalse.s loc_2B414
0x2b407  ldloc.2
0x2b408  ldloc.s  6
0x2b40a  ldfld    class Microsoft.ReportingServices.Library.RSStream Microsoft.ReportingServices.Library.ReportRenderingResult::Stream
0x2b40f  callvirt instance void Microsoft.ReportingServices.Library.StreamManager::AddSecondaryStream(class Microsoft.ReportingServices.Library.RSStream stream)
0x2b414  ldloc.s  4
0x2b416  ldc.i4.1
0x2b417  add
0x2b418  stloc.s  4
0x2b41a  ldloc.s  4
0x2b41c  ldloc.3
0x2b41d  ldlen
0x2b41e  conv.i4
0x2b41f  blt.s    loc_2B3DE
0x2b421  ldarg.0
0x2b422  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2b427  ldloc.1
0x2b428  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ReportRenderingResult::EffectiveParameters
0x2b42d  callvirt instance void Microsoft.ReportingServices.Library.ReportExecutionBase::set_EffectiveParameters(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection value)
0x2b432  br.s     loc_2B43E
0x2b434  ldstr    aCouldNotFindCa// "Could not find cached result"
0x2b439  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x2b43e  ldloc.1
0x2b43f  ret
```
