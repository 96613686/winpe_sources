# Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::PageInit

- ea: `0x73510`
- end: `0x73754`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::PageInit`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: `service_task, broker_com_uri`

## callers

- `0x73280`

## callees

- `0x73510`
- `0x761d0`
- `0x767e0`
- `0x76880`
- `0x77170`
- `0x778f0`
- `0x789b0`
- `0x79ca0`
- `0x79db0`
- `0x79dc0`
- `0x79de0`
- `0x79e00`
- `0x79e10`
- `0xef790`
- `0xf0e00`
- `0xf0ef0`
- `0xf10a0`
- `0x11daf0`
- `0x11db30`
- `0x11dfb0`
- `0x127b50`
- `0x1eb080`
- `0x1eb0c0`
- `0x1eb0e0`
- `0x1ed9b0`
- `0x1ed9d0`
- `0x1edcc0`
- `0x1edcd0`
- `0x1edd10`
- `0x1ede00`
- `0x1ee750`
- `0x1ee9f0`
- `0x1eea60`
- `0x1fb4f0`
- `0x1fc5b0`

## string_xrefs

- `0x73531`: `Missing cached BodyItemsForHeadFoot collection`
- `0x73549`: `Missing cached PageSectionItemsForHeadFoot collection`

## pseudocode

```c

```

## disassembly

```asm
0x73510  ldarg.0
0x73511  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::m_processingContext
0x73516  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportObjectModel()
0x7351b  stloc.0
0x7351c  ldloc.0
0x7351d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_AggregatesImpl()
0x73522  stloc.1
0x73523  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x73528  ldarg.1
0x73529  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_BodyItemsForHeadFoot()
0x7352e  ldnull
0x7352f  cgt.un
0x73531  ldstr    aMissingCachedB// "Missing cached BodyItemsForHeadFoot col"...
0x73536  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x7353b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x73540  ldarg.1
0x73541  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_PageSectionItemsForHeadFoot()
0x73546  ldnull
0x73547  cgt.un
0x73549  ldstr    aMissingCachedP// "Missing cached PageSectionItemsForHeadF"...
0x7354e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x73553  ldarg.1
0x73554  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_BodyItemsForHeadFoot()
0x73559  ldloca.s 6
0x7355b  initobj  Microsoft.ReportingServices.RdlExpressions.VariantResult
0x73561  ldloc.s  6
0x73563  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl::ResetAll(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult aResult)
0x73568  ldarg.1
0x73569  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_PageSectionItemsForHeadFoot()
0x7356e  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl::ResetAll()
0x73573  ldloc.0
0x73574  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.GlobalsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_GlobalsImpl()
0x73579  ldarg.0
0x7357a  ldfld    int32 Microsoft.ReportingServices.OnDemandReportRendering.PageEvaluation::m_currentPageNumber
0x7357f  ldarg.0
0x73580  ldfld    int32 Microsoft.ReportingServices.OnDemandReportRendering.PageEvaluation::m_totalPages
0x73585  ldarg.0
0x73586  ldfld    int32 Microsoft.ReportingServices.OnDemandReportRendering.PageEvaluation::m_currentOverallPageNumber
0x7358b  ldarg.0
0x7358c  ldfld    int32 Microsoft.ReportingServices.OnDemandReportRendering.PageEvaluation::m_overallTotalPages
0x73591  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.GlobalsImpl::SetPageNumbers(int32 pageNumber, int32 totalPages, int32 overallPageNumber, int32 overallTotalPages)
0x73596  ldloc.0
0x73597  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.GlobalsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_GlobalsImpl()
0x7359c  ldarg.0
0x7359d  ldfld    string Microsoft.ReportingServices.OnDemandReportRendering.PageEvaluation::m_pageName
0x735a2  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.GlobalsImpl::SetPageName(string pageName)
0x735a7  ldarg.0
0x735a8  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.OnDemandReportRendering.PageEvaluation::m_romReport
0x735ad  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Report Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportDef()
0x735b2  pop
0x735b3  ldarg.1
0x735b4  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportSection Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_SectionDef()
0x735b9  stloc.2
0x735ba  ldloc.2
0x735bb  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Page Microsoft.ReportingServices.ReportIntermediateFormat.ReportSection::get_Page()
0x735c0  stloc.3
0x735c1  ldarg.1
0x735c2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl>::.ctor()
0x735c7  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::set_PageAggregatesOverReportItems(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl> value)
0x735cc  ldarg.0
0x735cd  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::m_processingContext
0x735d2  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportObjectModel()
0x735d7  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_ReportItemsImpl()
0x735dc  ldc.i4.1
0x735dd  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl::set_SpecialMode(bool value)
0x735e2  ldloc.3
0x735e3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageAggregates()
0x735e8  brfalse  loc_736AD
0x735ed  ldc.i4.0
0x735ee  stloc.s  7
0x735f0  br       loc_7369B
0x735f5  ldloc.3
0x735f6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageAggregates()
0x735fb  ldloc.s  7
0x735fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::get_Item(!!T0)
0x73602  stloc.s  8
0x73604  ldloc.1
0x73605  ldloc.s  8
0x73607  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::Remove(class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo aggDef)
0x7360c  ldloc.s  8
0x7360e  ldc.i4.0
0x7360f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::set_ExprHostInitialized(bool value)
0x73614  ldloc.s  8
0x73616  ldarg.0
0x73617  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::m_processingContext
0x7361c  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo aggInfo, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x73621  stloc.s  9
0x73623  ldloc.s  9
0x73625  ldloca.s 0xA
0x73627  ldloca.s 0xB
0x73629  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::EvaluateParameters([out] object[]& values, [out] valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus& fieldStatus)
0x7362e  pop
0x7362f  ldloc.0
0x73630  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_ReportItemsImpl()
0x73635  callvirt instance string Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl::GetSpecialModeIndex()
0x7363a  stloc.s  0xC
0x7363c  ldloc.s  0xC
0x7363e  brtrue.s loc_7364A
0x73640  ldloc.1
0x73641  ldloc.s  9
0x73643  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::Add(class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj newObject)
0x73648  br.s     loc_7368E
0x7364a  ldarg.1
0x7364b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl> Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_PageAggregatesOverReportItems()
0x73650  ldloc.s  0xC
0x73652  ldloca.s 0xD
0x73654  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl>::TryGetValue(var<u1>, !!T0)
0x73659  brtrue.s loc_73677
0x7365b  ldarg.0
0x7365c  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::m_processingContext
0x73661  newobj   instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext)
0x73666  stloc.s  0xD
0x73668  ldarg.1
0x73669  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl> Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_PageAggregatesOverReportItems()
0x7366e  ldloc.s  0xC
0x73670  ldloc.s  0xD
0x73672  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl>::Add(var<u1>, !!T0)
0x73677  ldloc.s  0xD
0x73679  ldloc.s  9
0x7367b  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.AggregatesImpl::Add(class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj newObject)
0x73680  ldarg.0
0x73681  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.OnDemandReportRendering.ReportSection> Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::m_reportItemToReportSection
0x73686  ldloc.s  0xC
0x73688  ldarg.1
0x73689  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::set_Item(var<u1>, !!T0)
0x7368e  ldloc.s  9
0x73690  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::Init()
0x73695  ldloc.s  7
0x73697  ldc.i4.1
0x73698  add
0x73699  stloc.s  7
0x7369b  ldloc.s  7
0x7369d  ldloc.3
0x7369e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageAggregates()
0x736a3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::get_Count()
0x736a8  blt      loc_735F5
0x736ad  ldloc.0
0x736ae  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_ReportItemsImpl()
0x736b3  ldc.i4.0
0x736b4  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ReportItemsImpl::set_SpecialMode(bool value)
0x736b9  ldnull
0x736ba  stloc.s  4
0x736bc  ldnull
0x736bd  stloc.s  5
0x736bf  ldloc.2
0x736c0  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Page Microsoft.ReportingServices.ReportIntermediateFormat.ReportSection::get_Page()
0x736c5  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.PageSection Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageHeader()
0x736ca  brfalse.s loc_73700
0x736cc  ldloc.2
0x736cd  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Page Microsoft.ReportingServices.ReportIntermediateFormat.ReportSection::get_Page()
0x736d2  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.PageSection Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageHeader()
0x736d7  stloc.s  4
0x736d9  ldarg.1
0x736da  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Page Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Page()
0x736df  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.PageSection Microsoft.ReportingServices.OnDemandReportRendering.Page::get_PageHeader()
0x736e4  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.PageSectionInstance Microsoft.ReportingServices.OnDemandReportRendering.PageSection::get_Instance()
0x736e9  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.IReportScopeInstance Microsoft.ReportingServices.OnDemandReportRendering.BaseInstance::get_ReportScopeInstance()
0x736ee  stloc.s  5
0x736f0  ldarg.1
0x736f1  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Page Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Page()
0x736f6  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.PageSection Microsoft.ReportingServices.OnDemandReportRendering.Page::get_PageHeader()
0x736fb  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::SetNewContext()
0x73700  ldloc.2
0x73701  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Page Microsoft.ReportingServices.ReportIntermediateFormat.ReportSection::get_Page()
0x73706  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.PageSection Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageFooter()
0x7370b  brfalse.s loc_73741
0x7370d  ldloc.2
0x7370e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Page Microsoft.ReportingServices.ReportIntermediateFormat.ReportSection::get_Page()
0x73713  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.PageSection Microsoft.ReportingServices.ReportIntermediateFormat.Page::get_PageFooter()
0x73718  stloc.s  4
0x7371a  ldarg.1
0x7371b  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Page Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Page()
0x73720  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.PageSection Microsoft.ReportingServices.OnDemandReportRendering.Page::get_PageFooter()
0x73725  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.PageSectionInstance Microsoft.ReportingServices.OnDemandReportRendering.PageSection::get_Instance()
0x7372a  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.IReportScopeInstance Microsoft.ReportingServices.OnDemandReportRendering.BaseInstance::get_ReportScopeInstance()
0x7372f  stloc.s  5
0x73731  ldarg.1
0x73732  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Page Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Page()
0x73737  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.PageSection Microsoft.ReportingServices.OnDemandReportRendering.Page::get_PageFooter()
0x7373c  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::SetNewContext()
0x73741  ldloc.2
0x73742  brfalse.s loc_73753
0x73744  ldarg.0
0x73745  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.OnDemandPageEvaluation::m_processingContext
0x7374a  ldloc.s  4
0x7374c  ldloc.s  5
0x7374e  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::SetupContext(class Microsoft.ReportingServices.ReportIntermediateFormat.IInstancePath rifObject, class Microsoft.ReportingServices.OnDemandReportRendering.IReportScopeInstance romInstance)
0x73753  ret
```
