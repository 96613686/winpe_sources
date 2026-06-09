# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnChartBegin

- ea: `0x10d0`
- end: `0x10fe`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnChartBegin`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x10d0`
- `0x5530`

## pseudocode

```c

```

## disassembly

```asm
0x10d0  ldarg.3
0x10d1  ldind.u1
0x10d2  stloc.0
0x10d3  ldloc.0
0x10d4  brtrue.s loc_10DF
0x10d6  ldarg.0
0x10d7  ldarg.1
0x10d8  ldarg.2
0x10d9  ldarg.3
0x10da  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnChartBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool outputChart, bool& walkChart)
0x10df  ldarg.3
0x10e0  ldind.u1
0x10e1  brfalse.s loc_10FD
0x10e3  ldloc.0
0x10e4  brtrue.s loc_10F4
0x10e6  ldarg.3
0x10e7  ldarg.0
0x10e8  ldarg.1
0x10e9  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x10ee  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x10f3  stind.i1
0x10f4  ldarg.0
0x10f5  ldarg.3
0x10f6  ldind.u1
0x10f7  ldarg.2
0x10f8  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x10fd  ret
```
