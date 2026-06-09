# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelReportItem

- ea: `0x8110`
- end: `0x812b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelReportItem`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x84c0`
- `0x8930`

## callees

- `0x8110`
- `0x8130`

## pseudocode

```c

```

## disassembly

```asm
0x8110  ldarg.0
0x8111  ldarg.1
0x8112  ldarg.0
0x8113  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x8118  ldarg.2
0x8119  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x811e  brfalse.s loc_812A
0x8120  ldarg.0
0x8121  ldarg.1
0x8122  ldc.i4.0
0x8123  ldarg.2
0x8124  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x8129  pop
0x812a  ret
```
