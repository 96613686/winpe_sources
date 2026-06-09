# Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnStateIndicatorStateNameBegin

- ea: `0x56b0`
- end: `0x56bf`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnStateIndicatorStateNameBegin`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1670`
- `0x1970`
- `0x43a0`
- `0x4930`

## callees

- `0x56b0`

## pseudocode

```c

```

## disassembly

```asm
0x56b0  ldarg.1
0x56b1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_StateDataElementOutput()
0x56b6  ldc.i4.1
0x56b7  bne.un.s loc_56BA
0x56b9  ret
0x56ba  ldarg.s  4
0x56bc  ldc.i4.1
0x56bd  stind.i1
0x56be  ret
```
