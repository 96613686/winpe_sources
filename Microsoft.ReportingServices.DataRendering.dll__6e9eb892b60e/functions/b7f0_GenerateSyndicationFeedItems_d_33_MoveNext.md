# <GenerateSyndicationFeedItems>d__33::MoveNext

- ea: `0xb7f0`
- end: `0xb927`
- name: `<GenerateSyndicationFeedItems>d__33::MoveNext`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x3260`
- `0x3270`
- `0x3430`
- `0x3760`
- `0x6d90`
- `0x6e80`
- `0xb7f0`

## pseudocode

```c

```

## disassembly

```asm
0xb7f0  ldarg.0
0xb7f1  ldfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb7f6  stloc.0
0xb7f7  ldarg.0
0xb7f8  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor <GenerateSyndicationFeedItems>d__33::<>4__this
0xb7fd  stloc.1
0xb7fe  ldloc.0
0xb7ff  switch   loc_B812, loc_B899, loc_B91E
0xb810  ldc.i4.0
0xb811  ret
0xb812  ldarg.0
0xb813  ldc.i4.m1
0xb814  stfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb819  ldarg.0
0xb81a  ldloc.1
0xb81b  call     instance valuetype [mscorlib]System.Nullable`1<unsigned int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::GetQueryValueTop()
0xb820  stfld    valuetype [mscorlib]System.Nullable`1<unsigned int32> <GenerateSyndicationFeedItems>d__33::<numTopItems>5__2
0xb825  ldarg.0
0xb826  ldflda   valuetype [mscorlib]System.Nullable`1<unsigned int32> <GenerateSyndicationFeedItems>d__33::<numTopItems>5__2
0xb82b  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int32>::get_HasValue()
0xb830  brfalse.s loc_B851
0xb832  ldarg.0
0xb833  ldfld    valuetype [mscorlib]System.Nullable`1<unsigned int32> <GenerateSyndicationFeedItems>d__33::<numTopItems>5__2
0xb838  stloc.2
0xb839  ldc.i4.0
0xb83a  stloc.3
0xb83b  ldloca.s 2
0xb83d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int32>::GetValueOrDefault()
0xb842  ldloc.3
0xb843  ceq
0xb845  ldloca.s 2
0xb847  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int32>::get_HasValue()
0xb84c  and
0xb84d  brfalse.s loc_B851
0xb84f  ldc.i4.0
0xb850  ret
0xb851  ldarg.0
0xb852  ldc.i4.0
0xb853  stfld    unsigned int32 <GenerateSyndicationFeedItems>d__33::<numItems>5__3
0xb858  ldloc.1
0xb859  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_dataRegionWalker
0xb85e  ldloc.1
0xb85f  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportItem
0xb864  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::InitializeDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0xb869  brfalse  loc_B925
0xb86e  ldloc.1
0xb86f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ResetRowState()
0xb874  br.s     loc_B8E5
0xb876  ldloc.1
0xb877  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::IsRowOnPath()
0xb87c  brfalse.s loc_B8DF
0xb87e  ldloc.1
0xb87f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddReportParametersToRowContent()
0xb884  ldarg.0
0xb885  ldloc.1
0xb886  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0xb88b  stfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem <GenerateSyndicationFeedItems>d__33::<>2__current
0xb890  ldarg.0
0xb891  ldc.i4.1
0xb892  stfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb897  ldc.i4.1
0xb898  ret
0xb899  ldarg.0
0xb89a  ldc.i4.m1
0xb89b  stfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb8a0  ldarg.0
0xb8a1  ldfld    unsigned int32 <GenerateSyndicationFeedItems>d__33::<numItems>5__3
0xb8a6  stloc.3
0xb8a7  ldarg.0
0xb8a8  ldloc.3
0xb8a9  ldc.i4.1
0xb8aa  add
0xb8ab  stfld    unsigned int32 <GenerateSyndicationFeedItems>d__33::<numItems>5__3
0xb8b0  ldarg.0
0xb8b1  ldflda   valuetype [mscorlib]System.Nullable`1<unsigned int32> <GenerateSyndicationFeedItems>d__33::<numTopItems>5__2
0xb8b6  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int32>::get_HasValue()
0xb8bb  brfalse.s loc_B8DF
0xb8bd  ldarg.0
0xb8be  ldfld    unsigned int32 <GenerateSyndicationFeedItems>d__33::<numItems>5__3
0xb8c3  ldarg.0
0xb8c4  ldfld    valuetype [mscorlib]System.Nullable`1<unsigned int32> <GenerateSyndicationFeedItems>d__33::<numTopItems>5__2
0xb8c9  stloc.2
0xb8ca  ldloca.s 2
0xb8cc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int32>::GetValueOrDefault()
0xb8d1  ceq
0xb8d3  ldloca.s 2
0xb8d5  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int32>::get_HasValue()
0xb8da  and
0xb8db  brfalse.s loc_B8DF
0xb8dd  ldc.i4.0
0xb8de  ret
0xb8df  ldloc.1
0xb8e0  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ResetRowState()
0xb8e5  ldloc.1
0xb8e6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_dataRegionWalker
0xb8eb  ldloc.1
0xb8ec  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportItem
0xb8f1  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkNextDataRegionOrMapRow(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0xb8f6  brtrue   loc_B876
0xb8fb  ldloc.1
0xb8fc  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::IsRowOnPath()
0xb901  brfalse.s loc_B925
0xb903  ldloc.1
0xb904  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddReportParametersToRowContent()
0xb909  ldarg.0
0xb90a  ldloc.1
0xb90b  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0xb910  stfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem <GenerateSyndicationFeedItems>d__33::<>2__current
0xb915  ldarg.0
0xb916  ldc.i4.2
0xb917  stfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb91c  ldc.i4.1
0xb91d  ret
0xb91e  ldarg.0
0xb91f  ldc.i4.m1
0xb920  stfld    int32 <GenerateSyndicationFeedItems>d__33::<>1__state
0xb925  ldc.i4.0
0xb926  ret
```
