# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnGaugePanelBegin

- ea: `0x1100`
- end: `0x1125`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::OnGaugePanelBegin`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1000`
- `0x1040`
- `0x1100`
- `0x55d0`

## pseudocode

```c

```

## disassembly

```asm
0x1100  ldarg.0
0x1101  ldarg.1
0x1102  ldarg.2
0x1103  ldarg.3
0x1104  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugePanelBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel gaugePanel, bool outputGaugePanelData, bool& walkGaugePanel)
0x1109  ldarg.3
0x110a  ldind.u1
0x110b  brfalse.s loc_1124
0x110d  ldarg.3
0x110e  ldarg.0
0x110f  ldarg.1
0x1110  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x1115  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::IsPartOfDefinitionPathSteps(string definitionPath)
0x111a  stind.i1
0x111b  ldarg.0
0x111c  ldarg.3
0x111d  ldind.u1
0x111e  ldarg.2
0x111f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow(bool walk, bool output)
0x1124  ret
```
