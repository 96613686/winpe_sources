# Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMinutes

- ea: `0xf5f0`
- end: `0xf60c`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMinutes`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1b0`
- `0xdf70`

## callees

- `0xed40`
- `0xf380`
- `0xf5f0`

## pseudocode

```c

```

## disassembly

```asm
0xf5f0  ldarg.1
0xf5f1  ldc.i4.1
0xf5f2  bge.s    loc_F5FF
0xf5f4  ldstr    aMinutesinterva// "MinutesInterval"
0xf5f9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf5fe  throw
0xf5ff  ldarg.0
0xf600  ldarg.1
0xf601  newobj   instance void Microsoft.ReportingServices.Diagnostics.Minutes::.ctor(int32 minutesInterval)
0xf606  call     instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData(class Microsoft.ReportingServices.Diagnostics.BaseTriggerData value)
0xf60b  ret
```
