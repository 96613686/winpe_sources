# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkSubReport

- ea: `0x7260`
- end: `0x7312`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkSubReport`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x5780`
- `0x5790`
- `0x7260`
- `0x7550`

## pseudocode

```c

```

## disassembly

```asm
0x7260  ldarg.1
0x7261  brtrue.s loc_7264
0x7263  ret
0x7264  ldc.i4.0
0x7265  stloc.0
0x7266  ldarg.0
0x7267  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x726c  ldarg.1
0x726d  ldloca.s 0
0x726f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnSubReportBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport subReport, bool& walkSubreport)
0x7274  ldloc.0
0x7275  brfalse  loc_7311
0x727a  ldarg.1
0x727b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x7280  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance
0x7285  stloc.1
0x7286  ldloc.1
0x7287  brfalse.s loc_7305
0x7289  ldloc.1
0x728a  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance::get_ProcessedWithError()
0x728f  brtrue.s loc_72F9
0x7291  ldarg.1
0x7292  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport::get_Report()
0x7297  brfalse.s loc_7305
0x7299  ldarg.1
0x729a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport::get_Report()
0x729f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x72a4  brfalse.s loc_7305
0x72a6  ldarg.1
0x72a7  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport::get_Report()
0x72ac  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x72b1  stloc.2
0x72b2  ldc.i4.0
0x72b3  stloc.3
0x72b4  br.s     loc_72EE
0x72b6  ldloc.2
0x72b7  ldloc.3
0x72b8  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Item(!!T0)
0x72bd  stloc.s  4
0x72bf  ldloc.s  4
0x72c1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x72c6  brfalse.s loc_72EA
0x72c8  ldloc.s  4
0x72ca  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x72cf  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body::get_ReportItemCollection()
0x72d4  brfalse.s loc_72EA
0x72d6  ldarg.0
0x72d7  ldloc.s  4
0x72d9  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x72de  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body::get_ReportItemCollection()
0x72e3  ldarg.2
0x72e4  ldarg.3
0x72e5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItemCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection reportItemCollection, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x72ea  ldloc.3
0x72eb  ldc.i4.1
0x72ec  add
0x72ed  stloc.3
0x72ee  ldloc.3
0x72ef  ldloc.2
0x72f0  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Count()
0x72f5  blt.s    loc_72B6
0x72f7  br.s     loc_7305
0x72f9  ldloc.1
0x72fa  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReportInstance::get_ErrorMessage()
0x72ff  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x7304  throw
0x7305  ldarg.0
0x7306  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x730b  ldarg.1
0x730c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnSubReportEnd(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport subReport)
0x7311  ret
```
