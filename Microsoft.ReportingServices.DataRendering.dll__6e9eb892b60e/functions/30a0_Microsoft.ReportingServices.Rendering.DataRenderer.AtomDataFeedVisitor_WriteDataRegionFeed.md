# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed

- ea: `0x30a0`
- end: `0x30aa`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x2030`

## callees

- `0x30b0`

## pseudocode

```c

```

## disassembly

```asm
0x30a0  ldarg.0
0x30a1  ldarg.1
0x30a2  ldarg.2
0x30a3  ldnull
0x30a4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed(class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker dataRegionWalker, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, string feedName)
0x30a9  ret
```
