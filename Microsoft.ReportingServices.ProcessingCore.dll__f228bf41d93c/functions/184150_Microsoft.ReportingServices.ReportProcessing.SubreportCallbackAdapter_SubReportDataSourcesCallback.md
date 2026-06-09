# Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::SubReportDataSourcesCallback

- ea: `0x184150`
- end: `0x184216`
- name: `Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::SubReportDataSourcesCallback`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x175e50`
- `0x175e90`
- `0x178f30`
- `0x183fc0`
- `0x184150`
- `0x184270`
- `0x186990`
- `0x1869b0`
- `0x23f1a0`
- `0x23f1e0`
- `0x23f390`

## string_xrefs

- `0x1841a4`: `The subreport '{0}' could not be processed.  Parent report '{1}' failed to automatically republish, or it contains a Reporting Services 2005-style CustomReportItem, and is therefore incompatible with the subreport. To correct this error, please attempt to republish the parent report manually. If it contains a CustomReportItem, please upgrade the report to the latest version.`

## pseudocode

```c

```

## disassembly

```asm
0x184150  ldarg.s  4
0x184152  ldnull
0x184153  stind.ref
0x184154  ldnull
0x184155  stloc.0
0x184156  ldarg.0
0x184157  ldfld    class OnDemandSubReportDataSourcesCallback Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::m_subreportDataSourcesCallback
0x18415c  ldarg.1
0x18415d  ldarg.2
0x18415e  ldarg.0
0x18415f  ldftn    instance bool Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::NeedsUpgrade(valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags processingFlags)
0x184165  newobj   instance void NeedsUpgrade::.ctor(object object, native int method)
0x18416a  ldarg.3
0x18416b  ldloca.s 0
0x18416d  ldarg.s  5
0x18416f  ldloca.s 1
0x184171  callvirt instance void OnDemandSubReportDataSourcesCallback::Invoke(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext reportContext, string subreportPath, class NeedsUpgrade upgradeCheck, [out] class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext& subreportContext, [out] class Microsoft.ReportingServices.ReportProcessing.IChunkFactory& getCompiledDefinitionCallback, [out] class Microsoft.ReportingServices.DataExtensions.DataSourceInfoCollection& dataSources, [out] class Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection& dataSetReferences)
0x184176  ldloc.0
0x184177  brfalse  loc_184202
0x18417c  ldloc.0
0x18417d  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags Microsoft.ReportingServices.ReportProcessing.IChunkFactory::get_ReportProcessingFlags()
0x184182  ldc.i4.1
0x184183  call     bool Microsoft.ReportingServices.ReportProcessing.ReportProcessing::ContainsFlag(valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags processingFlags, valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags flag)
0x184188  brfalse.s loc_1841E9
0x18418a  ldarg.3
0x18418b  ldnull
0x18418c  stind.ref
0x18418d  ldarg.s  4
0x18418f  ldnull
0x184190  stind.ref
0x184191  ldarg.s  5
0x184193  ldnull
0x184194  stind.ref
0x184195  ldarg.2
0x184196  stloc.2
0x184197  ldarg.1
0x184198  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemPathAsString()
0x18419d  stloc.3
0x18419e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1841a3  ldc.i4.2
0x1841a4  ldstr    aTheSubreport0C_0// "The subreport '{0}' could not be proces"...
0x1841a9  ldc.i4.2
0x1841aa  newarr   [mscorlib]System.Object
0x1841af  dup
0x1841b0  ldc.i4.0
0x1841b1  ldloc.2
0x1841b2  stelem.ref
0x1841b3  dup
0x1841b4  ldc.i4.1
0x1841b5  ldloc.3
0x1841b6  stelem.ref
0x1841b7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1841bc  ldc.i4   0xFC
0x1841c1  ldc.i4.1
0x1841c2  newarr   [mscorlib]System.Object
0x1841c7  dup
0x1841c8  ldc.i4.0
0x1841c9  ldc.i4.8
0x1841ca  stloc.s  4
0x1841cc  ldloca.s 4
0x1841ce  constrained. Microsoft.ReportingServices.ReportProcessing.ObjectType
0x1841d4  callvirt instance string [mscorlib]System.Object::ToString()
0x1841d9  ldloc.2
0x1841da  ldnull
0x1841db  ldloc.2
0x1841dc  ldloc.3
0x1841dd  call     string Microsoft.ReportingServices.ReportProcessing.RPResWrapper::rsEngineMismatchParentReport(string objectType, string objectName, string propertyName, string subreportName, string parentReportPath)
0x1841e2  stelem.ref
0x1841e3  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, object[] arguments)
0x1841e8  throw
0x1841e9  ldloc.0
0x1841ea  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ChunkFactoryAdapter::.ctor(class Microsoft.ReportingServices.ReportProcessing.IChunkFactory aFactory)
0x1841ef  stloc.s  5
0x1841f1  ldarg.s  4
0x1841f3  ldloc.s  5
0x1841f5  ldftn    instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.ReportProcessing.ChunkFactoryAdapter::GetReportChunk(string name, valuetype ReportChunkTypes type, [out] string& mimeType)
0x1841fb  newobj   instance void GetReportChunk::.ctor(object object, native int method)
0x184200  stind.ref
0x184201  ret
0x184202  ldarg.3
0x184203  ldind.ref
0x184204  brtrue.s loc_184215
0x184206  ldarg.2
0x184207  ldarg.2
0x184208  call     string Microsoft.ReportingServices.ReportProcessing.RPResWrapper::rsMissingSubReport(string subreportName, string subreportPath)
0x18420d  ldc.i4.s 0x14
0x18420f  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(string errMessage, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0x184214  throw
0x184215  ret
```
