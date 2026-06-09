# Microsoft.ReportingServices.Diagnostics.Monthly::.ctor

- ea: `0xf010`
- end: `0xf025`
- name: `Microsoft.ReportingServices.Diagnostics.Monthly::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xf660`

## callees

- `0xea80`
- `0xefe0`
- `0xf000`

## pseudocode

```c

```

## disassembly

```asm
0xf010  ldarg.0
0xf011  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::.ctor()
0xf016  ldarg.0
0xf017  ldarg.1
0xf018  call     instance void Microsoft.ReportingServices.Diagnostics.Monthly::set_DaysOfMonth(unsigned int32 value)
0xf01d  ldarg.0
0xf01e  ldarg.2
0xf01f  call     instance void Microsoft.ReportingServices.Diagnostics.Monthly::set_Months(unsigned int32 value)
0xf024  ret
```
