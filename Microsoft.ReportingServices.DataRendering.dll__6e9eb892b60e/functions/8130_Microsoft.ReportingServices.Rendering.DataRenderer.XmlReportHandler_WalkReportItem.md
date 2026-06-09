# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem

- ea: `0x8130`
- end: `0x8227`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem`
- size: `247`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x80e0`
- `0x8110`
- `0x83d0`
- `0x84c0`
- `0x8670`
- `0x8930`

## callees

- `0x8030`
- `0x80a0`
- `0x8130`
- `0x8230`
- `0x82d0`
- `0x89e0`
- `0x93e0`
- `0x9b70`
- `0x9c60`

## pseudocode

```c

```

## disassembly

```asm
0x8130  ldarg.1
0x8131  brfalse.s loc_813C
0x8133  ldarg.1
0x8134  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x8139  ldc.i4.1
0x813a  bne.un.s loc_813E
0x813c  ldc.i4.0
0x813d  ret
0x813e  ldarg.1
0x813f  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox
0x8144  brfalse.s loc_8155
0x8146  ldarg.0
0x8147  ldarg.1
0x8148  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox
0x814d  ldarg.2
0x814e  ldarg.3
0x814f  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTextBox(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox tb, bool attributesOnly, bool firstInstance)
0x8154  ret
0x8155  ldarg.1
0x8156  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x815b  brfalse.s loc_8175
0x815d  ldarg.1
0x815e  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x8163  ldc.i4.2
0x8164  bne.un.s loc_8175
0x8166  ldarg.0
0x8167  ldarg.1
0x8168  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x816d  ldarg.2
0x816e  ldarg.3
0x816f  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRectangleContents(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle rect, bool attributesOnly, bool firstInstance)
0x8174  ret
0x8175  ldarg.1
0x8176  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x817b  brtrue.s loc_8198
0x817d  ldarg.1
0x817e  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x8183  brtrue.s loc_8198
0x8185  ldarg.1
0x8186  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegion
0x818b  brtrue.s loc_8198
0x818d  ldarg.1
0x818e  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x8193  brfalse  loc_8225
0x8198  ldarg.2
0x8199  brfalse.s loc_819D
0x819b  ldc.i4.1
0x819c  ret
0x819d  ldarg.1
0x819e  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x81a3  brfalse.s loc_81B4
0x81a5  ldarg.0
0x81a6  ldarg.1
0x81a7  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle
0x81ac  ldarg.3
0x81ad  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRectangle(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle rect, bool firstInstance)
0x81b2  br.s     loc_8225
0x81b4  ldarg.1
0x81b5  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix
0x81ba  brfalse.s loc_81CB
0x81bc  ldarg.0
0x81bd  ldarg.1
0x81be  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix
0x81c3  ldarg.3
0x81c4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablix(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool firstInstance)
0x81c9  br.s     loc_8225
0x81cb  ldarg.1
0x81cc  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart
0x81d1  brfalse.s loc_81E2
0x81d3  ldarg.0
0x81d4  ldarg.1
0x81d5  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart
0x81da  ldarg.3
0x81db  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChart(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool firstInstance)
0x81e0  br.s     loc_8225
0x81e2  ldarg.1
0x81e3  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel
0x81e8  brfalse.s loc_81F9
0x81ea  ldarg.0
0x81eb  ldarg.1
0x81ec  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel
0x81f1  ldarg.3
0x81f2  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePanel(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel gaugePanel, bool firstInstance)
0x81f7  br.s     loc_8225
0x81f9  ldarg.1
0x81fa  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x81ff  brfalse.s loc_8210
0x8201  ldarg.0
0x8202  ldarg.1
0x8203  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map
0x8208  ldarg.3
0x8209  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map map, bool firstInstance)
0x820e  br.s     loc_8225
0x8210  ldarg.1
0x8211  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x8216  brfalse.s loc_8225
0x8218  ldarg.0
0x8219  ldarg.1
0x821a  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport
0x821f  ldarg.3
0x8220  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkSubReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.SubReport sr, bool firstInstance)
0x8225  ldc.i4.0
0x8226  ret
```
