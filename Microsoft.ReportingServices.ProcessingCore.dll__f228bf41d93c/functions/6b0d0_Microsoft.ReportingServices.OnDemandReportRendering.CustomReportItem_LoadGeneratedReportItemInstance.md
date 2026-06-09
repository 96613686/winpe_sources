# Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::LoadGeneratedReportItemInstance

- ea: `0x6b0d0`
- end: `0x6b1f6`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::LoadGeneratedReportItemInstance`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x6afd0`

## callees

- `0x6b0b0`
- `0x6b0d0`
- `0x6b590`
- `0x75120`
- `0x77800`
- `0x77eb0`
- `0x792e0`
- `0x7dda0`
- `0x1250a0`
- `0x128650`
- `0x1286a0`
- `0x144de0`
- `0x145000`
- `0x145860`
- `0x184250`
- `0x1fb060`
- `0x1fb510`
- `0x200300`

## string_xrefs

- `0x6b1dc`: `!reader.HasReferences`

## pseudocode

```c

```

## disassembly

```asm
0x6b0d0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x6b0d5  ldarg.0
0x6b0d6  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_generatedReportItem
0x6b0db  brfalse.s loc_6B0ED
0x6b0dd  ldarg.0
0x6b0de  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_generatedReportItem
0x6b0e3  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x6b0e8  ldnull
0x6b0e9  cgt.un
0x6b0eb  br.s     loc_6B0EE
0x6b0ed  ldc.i4.0
0x6b0ee  ldstr    aMGeneratedrepo// "m_generatedReportItem != null && m_gene"...
0x6b0f3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6b0f8  ldarg.0
0x6b0f9  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportSize Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_dynamicWidth
0x6b0fe  brtrue.s loc_6B108
0x6b100  ldarg.0
0x6b101  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportSize Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_dynamicHeight
0x6b106  brfalse.s loc_6B10A
0x6b108  ldc.i4.0
0x6b109  ret
0x6b10a  ldarg.0
0x6b10b  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_RenderingContext()
0x6b110  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x6b115  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_OdpMetadata()
0x6b11a  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::get_ReportSnapshot()
0x6b11f  stloc.0
0x6b120  ldarg.0
0x6b121  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.CustomReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::get_CriDef()
0x6b126  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_RepeatWith()
0x6b12b  brfalse.s loc_6B157
0x6b12d  ldloc.0
0x6b12e  ldarg.0
0x6b12f  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::GetGeneratedInstanceChunkKey()
0x6b134  ldloca.s 1
0x6b136  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::TryGetImageChunkName(string definitionKey, [out] string& name)
0x6b13b  brtrue.s loc_6B13F
0x6b13d  ldc.i4.0
0x6b13e  ret
0x6b13f  ldarg.0
0x6b140  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_generatedReportItem
0x6b145  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x6b14a  castclass Microsoft.ReportingServices.OnDemandReportRendering.ImageInstance
0x6b14f  ldloc.1
0x6b150  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ImageInstance::set_StreamName(string value)
0x6b155  ldc.i4.1
0x6b156  ret
0x6b157  ldloc.0
0x6b158  ldarg.0
0x6b159  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::GetGeneratedInstanceChunkKey()
0x6b15e  ldloca.s 1
0x6b160  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ReportSnapshot::TryGetGeneratedReportItemChunkName(string definitionKey, [out] string& name)
0x6b165  brtrue.s loc_6B169
0x6b167  ldc.i4.0
0x6b168  ret
0x6b169  ldarg.0
0x6b16a  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_RenderingContext()
0x6b16f  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x6b174  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IChunkFactory Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ChunkFactory()
0x6b179  ldloc.1
0x6b17a  ldc.i4.s 0xA
0x6b17c  ldc.i4.0
0x6b17d  ldloca.s 2
0x6b17f  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.ReportProcessing.IChunkFactory::GetChunk(string chunkName, valuetype ReportChunkTypes type, valuetype Microsoft.ReportingServices.ReportProcessing.ChunkMode mode, [out] string& mimeType)
0x6b184  stloc.3
0x6b185  ldloc.3
0x6b186  brtrue.s loc_6B18A
0x6b188  ldc.i4.0
0x6b189  ret
0x6b18a  ldloc.3
0x6b18b  stloc.s  4
0x6b18d  ldarg.0
0x6b18e  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem::m_generatedReportItem
0x6b193  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x6b198  newobj   instance void Microsoft.ReportingServices.OnDemandReportRendering.ROMInstanceObjectCreator::.ctor(class Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance reportItemInstance)
0x6b19d  stloc.s  5
0x6b19f  ldloca.s 6
0x6b1a1  ldloc.3
0x6b1a2  ldloc.s  5
0x6b1a4  ldloc.s  5
0x6b1a6  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::.ctor(class [mscorlib]System.IO.Stream str, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IRIFObjectCreator rifObjectCreator, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceHelper persistenceHelper)
0x6b1ab  ldloca.s 6
0x6b1ad  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject()
0x6b1b2  stloc.s  7
0x6b1b4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x6b1b9  ldloc.s  7
0x6b1bb  isinst   Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance
0x6b1c0  ldnull
0x6b1c1  cgt.un
0x6b1c3  ldstr    aReportiteminst// "reportItemInstance is ReportItemInstanc"...
0x6b1c8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6b1cd  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x6b1d2  ldloca.s 6
0x6b1d4  call     instance bool Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::get_HasReferences()
0x6b1d9  ldc.i4.0
0x6b1da  ceq
0x6b1dc  ldstr    aReaderHasrefer// "!reader.HasReferences"
0x6b1e1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6b1e6  leave.s  loc_6B1F4
0x6b1e8  ldloc.s  4
0x6b1ea  brfalse.s loc_6B1F3
0x6b1ec  ldloc.s  4
0x6b1ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b1f3  endfinally
0x6b1f4  ldc.i4.1
0x6b1f5  ret
```
