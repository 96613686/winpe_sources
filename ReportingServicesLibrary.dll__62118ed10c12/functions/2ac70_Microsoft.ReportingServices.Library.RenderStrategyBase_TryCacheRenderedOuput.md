# Microsoft.ReportingServices.Library.RenderStrategyBase::TryCacheRenderedOuput

- ea: `0x2ac70`
- end: `0x2ad5e`
- name: `Microsoft.ReportingServices.Library.RenderStrategyBase::TryCacheRenderedOuput`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a530`

## callees

- `0x28bb0`
- `0x297a0`
- `0x297b0`
- `0x29800`
- `0x298a0`
- `0x2a820`
- `0x2a840`
- `0x2ab40`
- `0x2ac70`
- `0x2af60`
- `0x2c690`
- `0x5b2b0`
- `0x5b7f0`
- `0x5bb20`
- `0x5ea50`
- `0x5ff70`
- `0x609c0`

## string_xrefs

- `0x2ac97`: `Target Snapshot depends on user... will not add to local cache.`
- `0x2acae`: `Rendered result has interactive elements... will not add to local cache.`
- `0x2acc8`: `Rendered result had OnDemandExpression user profile dependency... will not add to local cache.`
- `0x2acd7`: `Adding rendering result to local cache...`

## pseudocode

```c

```

## disassembly

```asm
0x2ac70  ldarg.0
0x2ac71  call     instance class Microsoft.ReportingServices.Library.SnapshotManager Microsoft.ReportingServices.Library.RenderStrategyBase::get_SnapshotManager()
0x2ac76  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.SnapshotManager::get_ChunkTargetSnapshot()
0x2ac7b  stloc.0
0x2ac7c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x2ac81  ldloc.0
0x2ac82  ldnull
0x2ac83  cgt.un
0x2ac85  ldstr    aTargetsnapshot// "targetSnapshot"
0x2ac8a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2ac8f  ldloc.0
0x2ac90  callvirt instance bool Microsoft.ReportingServices.Library.ReportSnapshot::get_DependsOnUser()
0x2ac95  brfalse.s loc_2ACA6
0x2ac97  ldstr    aTargetSnapshot// "Target Snapshot depends on user... will"...
0x2ac9c  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x2aca1  br       loc_2AD5C
0x2aca6  ldarg.1
0x2aca7  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.OnDemandProcessingResult::get_HasInteractivity()
0x2acac  brfalse.s loc_2ACBD
0x2acae  ldstr    aRenderedResult// "Rendered result has interactive element"...
0x2acb3  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x2acb8  br       loc_2AD5C
0x2acbd  ldarg.0
0x2acbe  call     instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.UserProfileState Microsoft.ReportingServices.Library.RenderStrategyBase::get_UsedUserProfile()
0x2acc3  ldc.i4.8
0x2acc4  and
0x2acc5  ldc.i4.8
0x2acc6  bne.un.s loc_2ACD7
0x2acc8  ldstr    aRenderedResult_0// "Rendered result had OnDemandExpression "...
0x2accd  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x2acd2  br       loc_2AD5C
0x2acd7  ldstr    aAddingRenderin// "Adding rendering result to local cache."...
0x2acdc  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x2ace1  ldarg.1
0x2ace2  ldarg.0
0x2ace3  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2ace8  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ReportExecutionBase::get_EffectiveParameters()
0x2aced  ldarg.0
0x2acee  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2acf3  callvirt instance class Microsoft.ReportingServices.Library.ExecutionParameters Microsoft.ReportingServices.Library.ReportExecutionBase::get_RequestInfo()
0x2acf8  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.ExecutionParameters::Session
0x2acfd  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x2ad02  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x2ad07  ldarg.0
0x2ad08  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2ad0d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportExecutionBase::get_ExecutionDateTime()
0x2ad12  ldarg.0
0x2ad13  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2ad18  callvirt instance class Microsoft.ReportingServices.Library.IExecutionDataProvider Microsoft.ReportingServices.Library.ReportExecutionBase::get_DataProvider()
0x2ad1d  callvirt instance class Microsoft.ReportingServices.Library.StreamManager Microsoft.ReportingServices.Library.IExecutionDataProvider::get_StreamManager()
0x2ad22  newobj   instance void Microsoft.ReportingServices.Library.ReportRenderingResult::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.OnDemandProcessingResult processingResult, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection effectiveParameters, class Microsoft.ReportingServices.Library.ReportItem reportItem, valuetype [mscorlib]System.DateTime executionDateTime, class Microsoft.ReportingServices.Library.StreamManager streamManager)
0x2ad27  stloc.1
0x2ad28  ldsfld   class Microsoft.ReportingServices.Library.RSLocalCacheManager Microsoft.ReportingServices.Library.RSLocalCacheManager::Current
0x2ad2d  ldarg.0
0x2ad2e  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2ad33  callvirt instance class Microsoft.ReportingServices.Library.ExecutionParameters Microsoft.ReportingServices.Library.ReportExecutionBase::get_RequestInfo()
0x2ad38  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.ExecutionParameters::ReportContext
0x2ad3d  ldarg.0
0x2ad3e  call     instance class Microsoft.ReportingServices.Library.ReportExecutionBase Microsoft.ReportingServices.Library.RenderStrategyBase::get_ExecutionContext()
0x2ad43  callvirt instance class Microsoft.ReportingServices.Library.IExecutionDataProvider Microsoft.ReportingServices.Library.ReportExecutionBase::get_DataProvider()
0x2ad48  callvirt instance class Microsoft.ReportingServices.Library.StreamManager Microsoft.ReportingServices.Library.IExecutionDataProvider::get_StreamManager()
0x2ad4d  ldloc.1
0x2ad4e  ldarg.0
0x2ad4f  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.RenderStrategyBase::get_ReportExpirationDateTime()
0x2ad54  ldloc.0
0x2ad55  callvirt instance void Microsoft.ReportingServices.Library.RSLocalCacheManager::CacheRenderedResult(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext context, class Microsoft.ReportingServices.Library.StreamManager streamManager, class Microsoft.ReportingServices.Library.ReportRenderingResult result, valuetype [mscorlib]System.DateTime expirationDate, class Microsoft.ReportingServices.Library.ReportSnapshot reportSnapshot)
0x2ad5a  ldc.i4.1
0x2ad5b  ret
0x2ad5c  ldc.i4.0
0x2ad5d  ret
```
