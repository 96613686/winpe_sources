# Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::GenerateGroupTree

- ea: `0x210920`
- end: `0x21099f`
- name: `Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::GenerateGroupTree`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x225550`

## callees

- `0x1fb060`
- `0x1fb400`
- `0x1fb510`
- `0x1fb8a0`
- `0x1fb9f0`
- `0x1fba50`
- `0x1fc850`
- `0x2003c0`
- `0x200410`
- `0x210920`
- `0x2109a0`
- `0x225970`
- `0x2318e0`

## string_xrefs

- `0x210926`: `Data processing complete.  Beginning group tree creation`

## pseudocode

```c

```

## disassembly

```asm
0x210920  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x210925  ldc.i4.4
0x210926  ldstr    aDataProcessing// "Data processing complete.  Beginning gr"...
0x21092b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x210930  ldarg.0
0x210931  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210936  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_OdpMetadata()
0x21093b  stloc.0
0x21093c  ldloc.0
0x21093d  ldarg.0
0x21093e  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210943  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IChunkFactory Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ChunkFactory()
0x210948  ldloc.0
0x210949  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.GlobalIDOwnerCollection Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_GlobalIDOwnerCollection()
0x21094e  ldc.i4.0
0x21094f  ldarg.0
0x210950  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210955  callvirt instance int32 Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::GetActiveCompatibilityVersion()
0x21095a  ldarg.0
0x21095b  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210960  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ProhibitSerializableValues()
0x210965  call     void OnDemandProcessingManager::EnsureGroupTreeStorageSetup(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata odpMetadata, class Microsoft.ReportingServices.ReportProcessing.IChunkFactory chunkFactory, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.GlobalIDOwnerCollection globalIDOwnerCollection, bool openExisting, int32 rifCompatVersion, bool prohibitSerializableValues)
0x21096a  ldarg.0
0x21096b  call     instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::CreateInstances()
0x210970  ldarg.0
0x210971  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210976  callvirt instance bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_InSubreportInDataRegion()
0x21097b  brtrue.s loc_210993
0x21097d  ldarg.0
0x21097e  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_odpContext
0x210983  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_TopLevelContext()
0x210988  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::MergeNewUserSortFilterInformation()
0x21098d  ldloc.0
0x21098e  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::ResetUserSortFilterContexts()
0x210993  ldarg.0
0x210994  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeOnDemandDataSetObj Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataProcessingController::m_dataSetObj
0x210999  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeOnDemandDataSetObj::CompleteLookupProcessing()
0x21099e  ret
```
