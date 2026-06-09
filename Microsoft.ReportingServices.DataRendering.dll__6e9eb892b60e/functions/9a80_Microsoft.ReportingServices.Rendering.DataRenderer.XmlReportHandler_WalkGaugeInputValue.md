# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue

- ea: `0x9a80`
- end: `0x9ac9`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue`
- size: `73`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9540`
- `0x9600`
- `0x9700`
- `0x9840`
- `0x9980`

## callees

- `0x9a80`
- `0x9ad0`

## pseudocode

```c

```

## disassembly

```asm
0x9a80  ldarg.2
0x9a81  brtrue.s loc_9A84
0x9a83  ret
0x9a84  ldarg.2
0x9a85  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x9a8a  brfalse.s loc_9A9A
0x9a8c  ldarg.2
0x9a8d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_CompiledInstance()
0x9a92  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance::get_Value()
0x9a97  stloc.0
0x9a98  br.s     loc_9ABE
0x9a9a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x9a9f  ldarg.2
0x9aa0  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x9aa5  ldnull
0x9aa6  cgt.un
0x9aa8  ldstr    aGaugeinputvalu_0// "GaugeInputValue.Instance cannot be null"...
0x9aad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9ab2  ldarg.2
0x9ab3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_Instance()
0x9ab8  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValueInstance::get_Value()
0x9abd  stloc.0
0x9abe  ldarg.0
0x9abf  ldarg.1
0x9ac0  ldarg.2
0x9ac1  ldarg.3
0x9ac2  ldloc.0
0x9ac3  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance, object value)
0x9ac8  ret
```
