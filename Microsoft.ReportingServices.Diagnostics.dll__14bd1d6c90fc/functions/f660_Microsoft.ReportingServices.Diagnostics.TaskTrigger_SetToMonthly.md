# Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthly

- ea: `0xf660`
- end: `0xf67c`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMonthly`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1b0`
- `0xe0b0`

## callees

- `0xf010`
- `0xf380`
- `0xf660`

## pseudocode

```c

```

## disassembly

```asm
0xf660  ldarg.2
0xf661  brtrue.s loc_F66E
0xf663  ldstr    aDays// "Days"
0xf668  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0xf66d  throw
0xf66e  ldarg.0
0xf66f  ldarg.1
0xf670  ldarg.2
0xf671  newobj   instance void Microsoft.ReportingServices.Diagnostics.Monthly::.ctor(unsigned int32 daysOfMonth, unsigned int32 months)
0xf676  call     instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_TriggerData(class Microsoft.ReportingServices.Diagnostics.BaseTriggerData value)
0xf67b  ret
```
