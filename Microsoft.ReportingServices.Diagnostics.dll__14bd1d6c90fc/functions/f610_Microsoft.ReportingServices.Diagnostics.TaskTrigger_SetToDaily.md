# Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToDaily

- ea: `0xf610`
- end: `0xf62d`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToDaily`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1b0`
- `0xdfd0`

## callees

- `0xee00`
- `0xf380`
- `0xf610`

## pseudocode

```c

```

## disassembly

```asm
0xf610  ldarg.1
0xf611  ldc.i4.1
0xf612  conv.i8
0xf613  bge.s    loc_F620
0xf615  ldstr    aDaysinterval// "DaysInterval"
0xf61a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf61f  throw
0xf620  ldarg.0
0xf621  ldarg.1
0xf622  newobj   instance void Microsoft.ReportingServices.Diagnostics.Daily::.ctor(int64 daysInterval)
0xf627  call     instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData(class Microsoft.ReportingServices.Diagnostics.BaseTriggerData value)
0xf62c  ret
```
