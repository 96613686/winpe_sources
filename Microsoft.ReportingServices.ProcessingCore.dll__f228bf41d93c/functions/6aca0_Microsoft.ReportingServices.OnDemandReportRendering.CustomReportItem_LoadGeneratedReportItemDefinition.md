# Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::LoadGeneratedReportItemDefinition

- ea: `0x6aca0`
- end: `0x6adf5`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::LoadGeneratedReportItemDefinition`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ac30`

## callees

- `0x6aca0`
- `0x6b0a0`
- `0x6b540`
- `0x6b590`
- `0x75120`
- `0x77720`
- `0x77800`
- `0x77880`
- `0x778d0`
- `0x7efa0`
- `0x1248c0`
- `0x1248d0`
- `0x124a10`
- `0x124cc0`
- `0x124f10`
- `0x124f20`
- `0x125000`
- `0x1252a0`
- `0x1286a0`
- `0x134480`
- `0x144dd0`
- `0x145000`
- `0x145860`
- `0x14b760`
- `0x184250`
- `0x1fb060`
- `0x1fb510`
- `0x200300`

## string_xrefs

- `0x6ad2e`: `!reader.HasReferences`

## pseudocode

```c

```

## disassembly

```asm
0x6aca0  ldarg.0
0x6aca1  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_RenderingContext()
0x6aca6  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x6acab  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_OdpMetadata()
0x6acb0  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x6acb5  ldarg.0
0x6acb6  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::GetGeneratedDefinitionChunkKey()
0x6acbb  ldloca.s 0
0x6acbd  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::TryGetGeneratedReportItemChunkName(string definitionKey, [out] string& name)
0x6acc2  brtrue.s loc_6ACC6
0x6acc4  ldc.i4.0
0x6acc5  ret
0x6acc6  ldarg.0
0x6acc7  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_RenderingContext()
0x6accc  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x6acd1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IChunkFactory Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ChunkFactory()
0x6acd6  ldloc.0
0x6acd7  ldc.i4.s 0xA
0x6acd9  ldc.i4.0
0x6acda  ldloca.s 1
0x6acdc  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.ReportProcessing.IChunkFactory::GetChunk(string chunkName, valuetype ReportChunkTypes type, valuetype Microsoft.ReportingServices.ReportProcessing.ChunkMode mode, [out] string& mimeType)
0x6ace1  stloc.2
0x6ace2  ldloc.2
0x6ace3  brtrue.s loc_6ACE7
0x6ace5  ldc.i4.0
0x6ace6  ret
0x6ace7  ldloc.2
0x6ace8  stloc.3
0x6ace9  ldloca.s 4
0x6aceb  ldloc.2
0x6acec  ldarg.0
0x6aced  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::m_reportItemDef
0x6acf2  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner::get_ParentInstancePath()
0x6acf7  castclass Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner
0x6acfc  ldarg.0
0x6acfd  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::m_reportItemDef
0x6ad02  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Parent()
0x6ad07  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ProcessingRIFObjectCreator::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner parentIDOwner, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parentReportItem)
0x6ad0c  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::.ctor(class [mscorlib]System.IO.Stream str, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IRIFObjectCreator rifObjectCreator)
0x6ad11  ldloca.s 4
0x6ad13  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject()
0x6ad18  castclass Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem
0x6ad1d  stloc.s  5
0x6ad1f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x6ad24  ldloca.s 4
0x6ad26  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_HasReferences()
0x6ad2b  ldc.i4.0
0x6ad2c  ceq
0x6ad2e  ldstr    aReaderHasrefer// "!reader.HasReferences"
0x6ad33  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6ad38  ldloc.s  5
0x6ad3a  ldarg.0
0x6ad3b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::get_CriDef()
0x6ad40  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner::get_GlobalID()
0x6ad45  neg
0x6ad46  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner::set_GlobalID(int32 value)
0x6ad4b  ldloc.s  5
0x6ad4d  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_StyleClass()
0x6ad52  brfalse.s loc_6AD60
0x6ad54  ldloc.s  5
0x6ad56  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_StyleClass()
0x6ad5b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::InitializeForCRIGeneratedReportItem()
0x6ad60  ldloc.s  5
0x6ad62  ldarg.0
0x6ad63  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::m_reportItemDef
0x6ad68  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Visibility Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Visibility()
0x6ad6d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Visibility(class Microsoft.ReportingServices.ReportIntermediateFormat.Visibility value)
0x6ad72  ldloc.s  5
0x6ad74  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_ObjectType()
0x6ad79  ldc.i4.7
0x6ad7a  bne.un.s loc_6ADBC
0x6ad7c  ldarg.0
0x6ad7d  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.IReportScope Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::get_ParentScope()
0x6ad82  ldarg.0
0x6ad83  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.IDefinitionPath Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ParentDefinitionPath()
0x6ad88  ldarg.0
0x6ad89  ldfld    int32 Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_indexIntoParentCollectionDef
0x6ad8e  ldloc.s  5
0x6ad90  castclass Microsoft.ReportingServices.ReportIntermediateFormat.Image
0x6ad95  ldarg.0
0x6ad96  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_RenderingContext()
0x6ad9b  newobj   instance void Microsoft.ReportingServices.OnDemandReportRendering.Image::.ctor(class Microsoft.ReportingServices.OnDemandReportRendering.IReportScope reportScope, class Microsoft.ReportingServices.OnDemandReportRendering.IDefinitionPath parentDefinitionPath, int32 indexIntoParentCollectionDef, class Microsoft.ReportingServices.ReportIntermediateFormat.Image reportItemDef, class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext renderingContext)
0x6ada0  stloc.s  6
0x6ada2  ldloc.s  6
0x6ada4  ldarg.0
0x6ada5  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::set_CriOwner(class Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem value)
0x6adaa  ldloc.s  6
0x6adac  ldc.i4.0
0x6adad  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::set_CriGenerationPhase(valuetype CriGenerationPhases value)
0x6adb2  ldarg.0
0x6adb3  ldloc.s  6
0x6adb5  stfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_generatedReportItem
0x6adba  leave.s  loc_6ADF3
0x6adbc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x6adc1  ldc.i4.0
0x6adc2  ldstr    aUnexpectedCriG// "Unexpected CRI generated report item ty"...
0x6adc7  ldloc.s  5
0x6adc9  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_ObjectType()
0x6adce  stloc.s  7
0x6add0  ldloca.s 7
0x6add2  constrained. Microsoft.ReportingServices.ReportProcessing.ObjectType
0x6add8  callvirt instance string [mscorlib]System.Object::ToString()
0x6addd  call     string [mscorlib]System.String::Concat(string, string)
0x6ade2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6ade7  leave.s  loc_6ADF3
0x6ade9  ldloc.3
0x6adea  brfalse.s loc_6ADF2
0x6adec  ldloc.3
0x6aded  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6adf2  endfinally
0x6adf3  ldc.i4.1
0x6adf4  ret
```
