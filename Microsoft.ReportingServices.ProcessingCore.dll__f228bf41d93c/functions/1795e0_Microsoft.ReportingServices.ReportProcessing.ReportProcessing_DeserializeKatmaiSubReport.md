# Microsoft.ReportingServices.ReportProcessing.ReportProcessing::DeserializeKatmaiSubReport

- ea: `0x1795e0`
- end: `0x1797a1`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportProcessing::DeserializeKatmaiSubReport`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x179460`

## callees

- `0xda6c0`
- `0xdaa10`
- `0xdaa50`
- `0xdaa60`
- `0xdaa70`
- `0xdaa80`
- `0xdaa90`
- `0xdaaa0`
- `0xdaab0`
- `0xdaad0`
- `0xdaae0`
- `0x124ca0`
- `0x1252a0`
- `0x1356f0`
- `0x135700`
- `0x135730`
- `0x135750`
- `0x135770`
- `0x135790`
- `0x135c50`
- `0x1767c0`
- `0x178f30`
- `0x1795e0`
- `0x179d50`
- `0x184270`
- `0x23f150`
- `0x23f1e0`

## string_xrefs

- `0x1796d1`: `CompiledDefinition`
- `0x179708`: `CompiledDefinition`
- `0x179675`: `The subreport '{0}' could not be processed within parent report '{1}' due to a mismatch in execution engines. Either the subreport failed to automatically republish, or the subreport contains a Reporting Services 2005-style CustomReportItem. To correct this error, please attempt to republish the subreport manually. If it contains a CustomReportItem, please upgrade the report to the latest version.`
- `0x179782`: `IncompatibleFormatVersion`

## pseudocode

```c

```

## disassembly

```asm
0x1795e0  ldarg.s  4
0x1795e2  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo::get_CommonSubReportInfo()
0x1795e7  stloc.s  5
0x1795e9  ldloc.s  5
0x1795eb  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IChunkFactory Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_DefinitionChunkFactory()
0x1795f0  brtrue   loc_1796F9
0x1795f5  ldarg.s  5
0x1795f7  brfalse.s loc_17962F
0x1795f9  ldarg.1
0x1795fa  stloc.2
0x1795fb  ldloc.s  5
0x1795fd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_DefinitionUniqueName()
0x179602  stloc.s  4
0x179604  ldarg.0
0x179605  ldarg.2
0x179606  ldloc.s  5
0x179608  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_ReportPath()
0x17960d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::GetSubreportContext(string)
0x179612  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_ReportContext(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext value)
0x179617  ldloc.s  5
0x179619  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_RetrievalFailed()
0x17961e  brfalse  loc_1796EF
0x179623  ldarg.0
0x179624  ldc.i4.2
0x179625  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_RetrievalStatus(valuetype Status value)
0x17962a  leave    loc_1797A0
0x17962f  ldarg.3
0x179630  ldarg.2
0x179631  ldarg.0
0x179632  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::get_ReportName()
0x179637  ldloc.s  5
0x179639  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_DefinitionUniqueName()
0x17963e  ldnull
0x17963f  ldftn    bool Microsoft.ReportingServices.ReportProcessing.ReportProcessing::NeedsUpgradeImpl(valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags flags)
0x179645  newobj   instance void NeedsUpgrade::.ctor(object object, native int method)
0x17964a  ldarg.s  9
0x17964c  ldloca.s 0
0x17964e  ldloca.s 1
0x179650  ldloca.s 2
0x179652  ldloca.s 3
0x179654  callvirt instance void OnDemandSubReportCallback::Invoke(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext reportContext, string subreportPath, string newChunkName, class NeedsUpgrade upgradeCheck, class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parentQueryParameters, [out] class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext& subreportContext, [out] string& description, [out] class Microsoft.ReportingServices.ReportProcessing.IChunkFactory& getCompiledDefinitionCallback, [out] class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection& parameters)
0x179659  ldloc.2
0x17965a  brtrue.s loc_179661
0x17965c  leave    loc_1797A0
0x179661  ldloc.2
0x179662  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags Microsoft.ReportingServices.ReportProcessing.IChunkFactory::get_ReportProcessingFlags()
0x179667  ldc.i4.1
0x179668  call     bool Microsoft.ReportingServices.ReportProcessing.ReportProcessing::ContainsFlag(valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags processingFlags, valuetype Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags flag)
0x17966d  brtrue.s loc_1796D1
0x17966f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x179674  ldc.i4.2
0x179675  ldstr    aTheSubreport0C// "The subreport '{0}' could not be proces"...
0x17967a  ldc.i4.2
0x17967b  newarr   [mscorlib]System.Object
0x179680  dup
0x179681  ldc.i4.0
0x179682  ldarg.0
0x179683  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::get_ReportName()
0x179688  stelem.ref
0x179689  dup
0x17968a  ldc.i4.1
0x17968b  ldarg.2
0x17968c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemPathAsString()
0x179691  stelem.ref
0x179692  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x179697  ldarg.s  6
0x179699  ldc.i4   0x172
0x17969e  ldc.i4.1
0x17969f  ldarg.0
0x1796a0  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_ObjectType()
0x1796a5  ldarg.0
0x1796a6  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x1796ab  ldnull
0x1796ac  ldc.i4.2
0x1796ad  newarr   [mscorlib]System.String
0x1796b2  dup
0x1796b3  ldc.i4.0
0x1796b4  ldarg.0
0x1796b5  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x1796ba  stelem.ref
0x1796bb  dup
0x1796bc  ldc.i4.1
0x1796bd  ldarg.2
0x1796be  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_ItemPathAsString()
0x1796c3  stelem.ref
0x1796c4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1796c9  pop
0x1796ca  ldarg.0
0x1796cb  ldc.i4.2
0x1796cc  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_RetrievalStatus(valuetype Status value)
0x1796d1  ldstr    aCompileddefini// "CompiledDefinition"
0x1796d6  stloc.s  4
0x1796d8  ldloc.s  5
0x1796da  ldloc.3
0x1796db  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::set_ParametersFromCatalog(class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection value)
0x1796e0  ldloc.s  5
0x1796e2  ldloc.1
0x1796e3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::set_Description(string value)
0x1796e8  ldarg.0
0x1796e9  ldloc.0
0x1796ea  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_ReportContext(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext value)
0x1796ef  ldloc.s  5
0x1796f1  ldloc.2
0x1796f2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::set_DefinitionChunkFactory(class Microsoft.ReportingServices.ReportProcessing.IChunkFactory value)
0x1796f7  br.s     loc_17973C
0x1796f9  ldarg.s  5
0x1796fb  brfalse.s loc_179708
0x1796fd  ldloc.s  5
0x1796ff  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_DefinitionUniqueName()
0x179704  stloc.s  4
0x179706  br.s     loc_17970F
0x179708  ldstr    aCompileddefini// "CompiledDefinition"
0x17970d  stloc.s  4
0x17970f  ldloc.s  5
0x179711  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IChunkFactory Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_DefinitionChunkFactory()
0x179716  stloc.2
0x179717  ldarg.0
0x179718  ldarg.2
0x179719  ldloc.s  5
0x17971b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_ReportPath()
0x179720  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::GetSubreportContext(string)
0x179725  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_ReportContext(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext value)
0x17972a  ldloc.s  5
0x17972c  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_RetrievalFailed()
0x179731  brfalse.s loc_17973C
0x179733  ldarg.0
0x179734  ldc.i4.2
0x179735  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_RetrievalStatus(valuetype Status value)
0x17973a  leave.s  loc_1797A0
0x17973c  ldarg.0
0x17973d  ldloc.s  5
0x17973f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_ParametersFromCatalog()
0x179744  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_ParametersFromCatalog(class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection value)
0x179749  ldarg.0
0x17974a  ldloc.s  5
0x17974c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::get_Description()
0x179751  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_Description(string value)
0x179756  ldarg.0
0x179757  ldloc.2
0x179758  ldloc.s  4
0x17975a  ldarg.s  5
0x17975c  ldarg.s  7
0x17975e  ldarg.0
0x17975f  ldarg.0
0x179760  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.ReportProcessing.ReportProcessing::DeserializeKatmaiReport(class Microsoft.ReportingServices.ReportProcessing.IChunkFactory chunkFactory, string chunkName, bool keepReferences, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.GlobalIDOwnerCollection globalIDOwnerCollection, class Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner parentIDOwner, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parentReportItem)
0x179765  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_Report(class Microsoft.ReportingServices.ReportIntermediateFormat.Report value)
0x17976a  ldarg.0
0x17976b  ldarg.s  4
0x17976d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::UpdateSubReportEventSourceGlobalDataSetIds(class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo subReportInfo)
0x179772  ldarg.0
0x179773  ldc.i4.4
0x179774  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_RetrievalStatus(valuetype Status value)
0x179779  leave.s  loc_1797A0
0x17977b  pop
0x17977c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x179781  ldc.i4.0
0x179782  ldstr    aIncompatiblefo// "IncompatibleFormatVersion"
0x179787  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x17978c  leave.s  loc_1797A0
0x17978e  pop
0x17978f  ldloc.s  5
0x179791  ldc.i4.1
0x179792  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::set_RetrievalFailed(bool value)
0x179797  ldarg.0
0x179798  ldc.i4.2
0x179799  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReport::set_RetrievalStatus(valuetype Status value)
0x17979e  rethrow
0x1797a0  ret
```
