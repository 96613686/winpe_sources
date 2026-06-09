# Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToWeekly

- ea: `0xf630`
- end: `0xf65c`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToWeekly`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1b0`
- `0xe030`

## callees

- `0xeef0`
- `0xf380`
- `0xf630`

## pseudocode

```c

```

## disassembly

```asm
0xf630  ldarg.1
0xf631  ldc.i4.0
0xf632  conv.i8
0xf633  bgt.s    loc_F640
0xf635  ldstr    aWeeksinterval// "WeeksInterval"
0xf63a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf63f  throw
0xf640  ldarg.2
0xf641  brtrue.s loc_F64E
0xf643  ldstr    aDaysofweek// "DaysOfWeek"
0xf648  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf64d  throw
0xf64e  ldarg.0
0xf64f  ldarg.1
0xf650  ldarg.2
0xf651  newobj   instance void Microsoft.ReportingServices.Diagnostics.Weekly::.ctor(int64 weeksInterval, unsigned int32 daysOfWeek)
0xf656  call     instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData(class Microsoft.ReportingServices.Diagnostics.BaseTriggerData value)
0xf65b  ret
```
