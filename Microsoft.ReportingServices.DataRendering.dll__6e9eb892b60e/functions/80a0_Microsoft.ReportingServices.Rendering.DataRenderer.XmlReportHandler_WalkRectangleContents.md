# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRectangleContents

- ea: `0x80a0`
- end: `0x80b6`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRectangleContents`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8080`
- `0x8130`

## callees

- `0x80a0`
- `0x80e0`

## pseudocode

```c

```

## disassembly

```asm
0x80a0  ldarg.1
0x80a1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle::get_ReportItemCollection()
0x80a6  stloc.0
0x80a7  ldloc.0
0x80a8  brtrue.s loc_80AC
0x80aa  ldc.i4.0
0x80ab  ret
0x80ac  ldarg.0
0x80ad  ldloc.0
0x80ae  ldarg.2
0x80af  ldarg.3
0x80b0  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItemCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection ric, bool attributesOnly, bool firstInstance)
0x80b5  ret
```
