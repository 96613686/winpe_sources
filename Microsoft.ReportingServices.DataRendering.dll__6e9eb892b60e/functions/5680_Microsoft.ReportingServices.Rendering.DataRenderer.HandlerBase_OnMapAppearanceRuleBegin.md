# Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapAppearanceRuleBegin

- ea: `0x5680`
- end: `0x5692`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnMapAppearanceRuleBegin`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1630`
- `0x1920`
- `0x4330`
- `0x48e0`

## callees

- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x5680  ldarg.1
0x5681  brfalse.s loc_568C
0x5683  ldarg.1
0x5684  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapAppearanceRule::get_DataElementOutput()
0x5689  ldc.i4.1
0x568a  bne.un.s loc_568D
0x568c  ret
0x568d  ldarg.s  4
0x568f  ldc.i4.1
0x5690  stind.i1
0x5691  ret
```
