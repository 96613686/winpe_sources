# Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugeInputValueBegin

- ea: `0x55f0`
- end: `0x55ff`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnGaugeInputValueBegin`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1530`
- `0x18a0`
- `0x4290`
- `0x47f0`

## callees

- `0x55f0`

## pseudocode

```c

```

## disassembly

```asm
0x55f0  ldarg.1
0x55f1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_DataElementOutput()
0x55f6  ldc.i4.1
0x55f7  bne.un.s loc_55FA
0x55f9  ret
0x55fa  ldarg.s  5
0x55fc  ldc.i4.1
0x55fd  stind.i1
0x55fe  ret
```
