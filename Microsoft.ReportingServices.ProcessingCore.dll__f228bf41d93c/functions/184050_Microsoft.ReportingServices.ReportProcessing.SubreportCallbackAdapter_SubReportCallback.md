# Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::SubReportCallback

- ea: `0x184050`
- end: `0x18414e`
- name: `Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::SubReportCallback`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x175e50`
- `0x175e90`
- `0x1767c0`
- `0x178f30`
- `0x183fc0`
- `0x184050`
- `0x184270`
- `0x186990`
- `0x1869b0`
- `0x23f150`
- `0x23f1e0`
- `0x23f390`

## string_xrefs

- `0x1840ad`: `The subreport '{0}' could not be processed.  Parent report '{1}' failed to automatically republish, or it contains a Reporting Services 2005-style CustomReportItem, and is therefore incompatible with the subreport. To correct this error, please attempt to republish the parent report manually. If it contains a CustomReportItem, please upgrade the report to the latest version.`

## pseudocode

```c

```

## disassembly

```asm
0x184050  ldarg.s  5
0x184052  ldnull
0x184053  stind.ref
0x184054  ldnull
0x184055  stloc.0
0x184056  ldarg.0
0x184057  ldfld    class OnDemandSubReportCallback Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::m_subreportCallback
0x18405c  ldarg.1
0x18405d  ldarg.2
0x18405e  ldnull
0x18405f  ldarg.0
0x184060  ldftn    instance bool Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::NeedsUpgrade(valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags processingFlags)
0x184066  newobj   instance void NeedsUpgrade::.ctor(object object, native int method)
0x18406b  ldnull
0x18406c  ldarg.3
0x18406d  ldarg.s  4
0x18406f  ldloca.s 0
0x184071  ldarg.s  6
0x184073  callvirt instance void OnDemandSubReportCallback::Invoke(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext reportContext, string subreportPath, string newChunkName, class NeedsUpgrade upgradeCheck, class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parentQueryParameters, [out] class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext& subreportContext, [out] string& description, [out] class Microsoft.ReportingServices.ReportProcessing.IChunkFactory& getCompiledDefinitionCallback, [out] class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection& parameters)
0x184078  ldloc.0
0x184079  brfalse  loc_18413A
0x18407e  ldloc.0
0x18407f  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags Microsoft.ReportingServices.ReportProcessing.IChunkFactory::get_ReportProcessingFlags()
0x184084  ldc.i4.1
0x184085  call     bool Microsoft.ReportingServices.ReportProcessing.ReportProcessing::ContainsFlag(valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags processingFlags, valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags flag)
0x18408a  brfalse  loc_184121
0x18408f  ldarg.3
0x184090  ldnull
0x184091  stind.ref
0x184092  ldarg.s  4
0x184094  ldnull
0x184095  stind.ref
0x184096  ldarg.s  5
0x184098  ldnull
0x184099  stind.ref
0x18409a  ldarg.s  6
0x18409c  ldnull
0x18409d  stind.ref
0x18409e  ldarg.2
0x18409f  stloc.1
0x1840a0  ldarg.1
0x1840a1  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemPathAsString()
0x1840a6  stloc.2
0x1840a7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1840ac  ldc.i4.2
0x1840ad  ldstr    aTheSubreport0C_0// "The subreport '{0}' could not be proces"...
0x1840b2  ldc.i4.2
0x1840b3  newarr   [mscorlib]System.Object
0x1840b8  dup
0x1840b9  ldc.i4.0
0x1840ba  ldloc.1
0x1840bb  stelem.ref
0x1840bc  dup
0x1840bd  ldc.i4.1
0x1840be  ldloc.2
0x1840bf  stelem.ref
0x1840c0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1840c5  ldarg.0
0x1840c6  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::m_errorContext
0x1840cb  brfalse.s loc_1840F0
0x1840cd  ldarg.0
0x1840ce  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.ReportProcessing.SubreportCallbackAdapter::m_errorContext
0x1840d3  ldc.i4   0x173
0x1840d8  ldc.i4.1
0x1840d9  ldc.i4.8
0x1840da  ldloc.1
0x1840db  ldnull
0x1840dc  ldc.i4.2
0x1840dd  newarr   [mscorlib]System.String
0x1840e2  dup
0x1840e3  ldc.i4.0
0x1840e4  ldloc.1
0x1840e5  stelem.ref
0x1840e6  dup
0x1840e7  ldc.i4.1
0x1840e8  ldloc.2
0x1840e9  stelem.ref
0x1840ea  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1840ef  pop
0x1840f0  ldc.i4   0xFC
0x1840f5  ldc.i4.1
0x1840f6  newarr   [mscorlib]System.Object
0x1840fb  dup
0x1840fc  ldc.i4.0
0x1840fd  ldc.i4.8
0x1840fe  stloc.3
0x1840ff  ldloca.s 3
0x184101  constrained. Microsoft.ReportingServices.ReportProcessing.ObjectType
0x184107  callvirt instance string [mscorlib]System.Object::ToString()
0x18410c  ldarg.2
0x18410d  ldnull
0x18410e  ldarg.2
0x18410f  ldarg.1
0x184110  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemPathAsString()
0x184115  call     string Microsoft.ReportingServices.ReportProcessing.RPResWrapper::rsEngineMismatchParentReport(string objectType, string objectName, string propertyName, string subreportName, string parentReportPath)
0x18411a  stelem.ref
0x18411b  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, object[] arguments)
0x184120  throw
0x184121  ldloc.0
0x184122  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ChunkFactoryAdapter::.ctor(class Microsoft.ReportingServices.ReportProcessing.IChunkFactory aFactory)
0x184127  stloc.s  4
0x184129  ldarg.s  5
0x18412b  ldloc.s  4
0x18412d  ldftn    instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.ReportProcessing.ChunkFactoryAdapter::GetReportChunk(string name, valuetype ReportChunkTypes type, [out] string& mimeType)
0x184133  newobj   instance void GetReportChunk::.ctor(object object, native int method)
0x184138  stind.ref
0x184139  ret
0x18413a  ldarg.3
0x18413b  ldind.ref
0x18413c  brtrue.s loc_18414D
0x18413e  ldarg.2
0x18413f  ldarg.2
0x184140  call     string Microsoft.ReportingServices.ReportProcessing.RPResWrapper::rsMissingSubReport(string subreportName, string subreportPath)
0x184145  ldc.i4.s 0x14
0x184147  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(string errMessage, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code)
0x18414c  throw
0x18414d  ret
```
