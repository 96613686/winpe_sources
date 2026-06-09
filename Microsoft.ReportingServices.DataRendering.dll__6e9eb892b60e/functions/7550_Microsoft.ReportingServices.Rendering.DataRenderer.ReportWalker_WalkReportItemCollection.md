# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItemCollection

- ea: `0x7550`
- end: `0x75ca`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItemCollection`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6f70`
- `0x7260`
- `0x7320`

## callees

- `0x57e0`
- `0x7390`
- `0x7550`

## pseudocode

```c

```

## disassembly

```asm
0x7550  ldarg.1
0x7551  brtrue.s loc_7554
0x7553  ret
0x7554  ldc.i4.0
0x7555  stloc.0
0x7556  br.s     loc_75C0
0x7558  ldarg.1
0x7559  ldloc.0
0x755a  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem>::get_Item(!!T0)
0x755f  stloc.1
0x7560  ldloc.1
0x7561  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegion
0x7566  brtrue.s loc_7570
0x7568  ldloc.1
0x7569  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x756e  brfalse.s loc_75B3
0x7570  ldarg.0
0x7571  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_walkTopLevelOnly
0x7576  brfalse.s loc_75B3
0x7578  ldloc.1
0x7579  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix
0x757e  brtrue.s loc_7598
0x7580  ldloc.1
0x7581  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart
0x7586  brtrue.s loc_7598
0x7588  ldloc.1
0x7589  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel
0x758e  brtrue.s loc_7598
0x7590  ldloc.1
0x7591  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x7596  brfalse.s loc_75BC
0x7598  ldarg.0
0x7599  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dataRegionsOrMaps
0x759e  ldloc.1
0x759f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x75a4  pop
0x75a5  ldarg.0
0x75a6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x75ab  ldloc.1
0x75ac  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnTopLevelDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x75b1  br.s     loc_75BC
0x75b3  ldarg.0
0x75b4  ldloc.1
0x75b5  ldarg.2
0x75b6  ldarg.3
0x75b7  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x75bc  ldloc.0
0x75bd  ldc.i4.1
0x75be  add
0x75bf  stloc.0
0x75c0  ldloc.0
0x75c1  ldarg.1
0x75c2  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem>::get_Count()
0x75c7  blt.s    loc_7558
0x75c9  ret
```
