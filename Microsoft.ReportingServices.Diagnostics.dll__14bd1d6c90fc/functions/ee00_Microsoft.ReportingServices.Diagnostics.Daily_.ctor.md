# Microsoft.ReportingServices.Diagnostics.Daily::.ctor

- ea: `0xee00`
- end: `0xee0e`
- name: `Microsoft.ReportingServices.Diagnostics.Daily::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xf610`

## callees

- `0xea80`
- `0xedf0`

## pseudocode

```c

```

## disassembly

```asm
0xee00  ldarg.0
0xee01  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::.ctor()
0xee06  ldarg.0
0xee07  ldarg.1
0xee08  call     instance void Microsoft.ReportingServices.Diagnostics.Daily::set_DaysInterval(int64 value)
0xee0d  ret
```
