# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MonthlyDOWEveryMonthScheduleDescription

- ea: `0x10610`
- end: `0x1061f`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MonthlyDOWEveryMonthScheduleDescription`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x164c0`

## string_xrefs

- `0x10610`: `MonthlyDOWEveryMonthScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x10610  ldstr    aMonthlydowever// "MonthlyDOWEveryMonthScheduleDescription"
0x10615  ldarg.0
0x10616  ldarg.1
0x10617  ldarg.2
0x10618  ldarg.3
0x10619  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0x1061e  ret
```
