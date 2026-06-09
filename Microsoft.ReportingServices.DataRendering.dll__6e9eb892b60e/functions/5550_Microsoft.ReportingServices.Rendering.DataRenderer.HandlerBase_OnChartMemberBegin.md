# Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartMemberBegin

- ea: `0x5550`
- end: `0x5576`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartMemberBegin`
- size: `38`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1250`
- `0x16f0`
- `0x2540`
- `0x40d0`
- `0x4450`

## callees

- `0x5550`

## pseudocode

```c

```

## disassembly

```asm
0x5550  ldarg.1
0x5551  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_DataElementOutput()
0x5556  ldc.i4.1
0x5557  bne.un.s loc_555A
0x5559  ret
0x555a  ldarg.1
0x555b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x5560  brfalse.s loc_5571
0x5562  ldarg.1
0x5563  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x5568  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_DataElementOutput()
0x556d  ldc.i4.1
0x556e  bne.un.s loc_5571
0x5570  ret
0x5571  ldarg.s  5
0x5573  ldc.i4.1
0x5574  stind.i1
0x5575  ret
```
