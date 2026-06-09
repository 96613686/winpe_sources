# Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthlyDOW

- ea: `0xf680`
- end: `0xf6ab`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthlyDOW`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1b0`
- `0xe140`

## callees

- `0xf270`
- `0xf380`
- `0xf680`

## pseudocode

```c

```

## disassembly

```asm
0xf680  ldarg.1
0xf681  brtrue.s loc_F68E
0xf683  ldstr    aWhichweek// "WhichWeek"
0xf688  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf68d  throw
0xf68e  ldarg.3
0xf68f  brtrue.s loc_F69C
0xf691  ldstr    aMonthsofyear// "MonthsOfYear"
0xf696  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf69b  throw
0xf69c  ldarg.0
0xf69d  ldarg.1
0xf69e  ldarg.2
0xf69f  ldarg.3
0xf6a0  newobj   instance void Microsoft.ReportingServices.Diagnostics.MonthlyDOW::.ctor(unsigned int32 week, unsigned int32 daysOfWeek, unsigned int32 months)
0xf6a5  call     instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData(class Microsoft.ReportingServices.Diagnostics.BaseTriggerData value)
0xf6aa  ret
```
