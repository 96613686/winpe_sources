# Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::CreateImageCacheManager

- ea: `0x1faf90`
- end: `0x1fafcf`
- name: `Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::CreateImageCacheManager`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1fa620`

## callees

- `0x1fa160`
- `0x1fa3d0`
- `0x1faf90`

## string_xrefs

- `0x1fafba`: `CreateImageCacheManager: invalid contextMode.`
- `0x1fafc4`: `CreateImageCacheManager: invalid contextMode.`

## pseudocode

```c

```

## disassembly

```asm
0x1faf90  ldarg.0
0x1faf91  switch   loc_1FAFAC, loc_1FAFA4, loc_1FAFAC
0x1fafa2  br.s     loc_1FAFB4
0x1fafa4  ldarg.1
0x1fafa5  ldarg.2
0x1fafa6  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.StreamingImageCacheManager::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata odpMetadata, class Microsoft.ReportingServices.ReportProcessing.IChunkFactory chunkFactory)
0x1fafab  ret
0x1fafac  ldarg.1
0x1fafad  ldarg.2
0x1fafae  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.SnapshotImageCacheManager::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata odpMetadata, class Microsoft.ReportingServices.ReportProcessing.IChunkFactory chunkFactory)
0x1fafb3  ret
0x1fafb4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1fafb9  ldc.i4.0
0x1fafba  ldstr    aCreateimagecac// "CreateImageCacheManager: invalid contex"...
0x1fafbf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1fafc4  ldstr    aCreateimagecac// "CreateImageCacheManager: invalid contex"...
0x1fafc9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1fafce  throw
```
