# Microsoft.ReportingServices.Diagnostics.Weekly::.ctor

- ea: `0xeef0`
- end: `0xef05`
- name: `Microsoft.ReportingServices.Diagnostics.Weekly::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xf630`

## callees

- `0xea80`
- `0xeec0`
- `0xeee0`

## pseudocode

```c

```

## disassembly

```asm
0xeef0  ldarg.0
0xeef1  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::.ctor()
0xeef6  ldarg.0
0xeef7  ldarg.1
0xeef8  call     instance void Microsoft.ReportingServices.Diagnostics.Weekly::set_WeeksInterval(int64 value)
0xeefd  ldarg.0
0xeefe  ldarg.2
0xeeff  call     instance void Microsoft.ReportingServices.Diagnostics.Weekly::set_DaysOfWeek(unsigned int32 value)
0xef04  ret
```
