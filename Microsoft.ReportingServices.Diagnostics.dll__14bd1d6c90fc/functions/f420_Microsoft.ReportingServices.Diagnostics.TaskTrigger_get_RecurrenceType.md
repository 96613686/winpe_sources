# Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType

- ea: `0xf420`
- end: `0xf477`
- name: `Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xdb40`
- `0xdc40`
- `0xea20`
- `0xf490`

## callees

- `0xf370`
- `0xf420`

## pseudocode

```c

```

## disassembly

```asm
0xf420  ldc.i4.1
0xf421  stloc.0
0xf422  ldarg.0
0xf423  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf428  isinst   Microsoft.ReportingServices.Diagnostics.Daily
0xf42d  brfalse.s loc_F433
0xf42f  ldc.i4.3
0xf430  stloc.0
0xf431  br.s     loc_F475
0xf433  ldarg.0
0xf434  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf439  isinst   Microsoft.ReportingServices.Diagnostics.Minutes
0xf43e  brfalse.s loc_F444
0xf440  ldc.i4.2
0xf441  stloc.0
0xf442  br.s     loc_F475
0xf444  ldarg.0
0xf445  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf44a  isinst   Microsoft.ReportingServices.Diagnostics.Weekly
0xf44f  brfalse.s loc_F455
0xf451  ldc.i4.4
0xf452  stloc.0
0xf453  br.s     loc_F475
0xf455  ldarg.0
0xf456  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf45b  isinst   Microsoft.ReportingServices.Diagnostics.Monthly
0xf460  brfalse.s loc_F466
0xf462  ldc.i4.5
0xf463  stloc.0
0xf464  br.s     loc_F475
0xf466  ldarg.0
0xf467  call     instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xf46c  isinst   Microsoft.ReportingServices.Diagnostics.MonthlyDOW
0xf471  brfalse.s loc_F475
0xf473  ldc.i4.6
0xf474  stloc.0
0xf475  ldloc.0
0xf476  ret
```
