# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnTablixMemberBegin

- ea: `0x1090`
- end: `0x10ce`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnTablixMemberBegin`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x1090`
- `0x54d0`

## pseudocode

```c

```

## disassembly

```asm
0x1090  ldarg.2
0x1091  ldind.u1
0x1092  stloc.0
0x1093  ldloc.0
0x1094  brtrue.s loc_109F
0x1096  ldarg.0
0x1097  ldarg.1
0x1098  ldarg.2
0x1099  ldarg.3
0x109a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnTablixMemberBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember tablixMember, bool& walkThisMember, bool outputThisMember)
0x109f  ldarg.2
0x10a0  ldind.u1
0x10a1  brfalse.s loc_10CD
0x10a3  ldarg.1
0x10a4  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x10a9  brfalse.s loc_10CD
0x10ab  ldarg.1
0x10ac  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x10b1  brfalse.s loc_10CD
0x10b3  ldloc.0
0x10b4  brtrue.s loc_10C4
0x10b6  ldarg.2
0x10b7  ldarg.0
0x10b8  ldarg.1
0x10b9  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_DefinitionPath()
0x10be  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x10c3  stind.i1
0x10c4  ldarg.0
0x10c5  ldarg.2
0x10c6  ldind.u1
0x10c7  ldarg.3
0x10c8  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x10cd  ret
```
