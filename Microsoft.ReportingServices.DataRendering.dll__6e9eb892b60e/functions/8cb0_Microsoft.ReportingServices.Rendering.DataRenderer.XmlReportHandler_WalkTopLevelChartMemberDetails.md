# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartMemberDetails

- ea: `0x8cb0`
- end: `0x8ccb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartMemberDetails`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8a80`
- `0x8d30`

## callees

- `0x8cb0`
- `0x8cd0`

## pseudocode

```c

```

## disassembly

```asm
0x8cb0  ldarg.0
0x8cb1  ldarg.1
0x8cb2  ldarg.0
0x8cb3  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x8cb8  ldarg.2
0x8cb9  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool attributesOnly, bool firstInstance)
0x8cbe  brfalse.s loc_8CCA
0x8cc0  ldarg.0
0x8cc1  ldarg.1
0x8cc2  ldc.i4.0
0x8cc3  ldarg.2
0x8cc4  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool attributesOnly, bool firstInstance)
0x8cc9  pop
0x8cca  ret
```
