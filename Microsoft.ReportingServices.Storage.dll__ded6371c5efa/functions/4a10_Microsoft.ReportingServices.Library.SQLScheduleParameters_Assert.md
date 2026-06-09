# Microsoft.ReportingServices.Library.SQLScheduleParameters::Assert

- ea: `0x4a10`
- end: `0x4a1d`
- name: `Microsoft.ReportingServices.Library.SQLScheduleParameters::Assert`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4a20`
- `0x4ac0`
- `0x4b40`

## pseudocode

```c

```

## disassembly

```asm
0x4a10  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x4a15  ldarg.1
0x4a16  ldarg.2
0x4a17  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x4a1c  ret
```
