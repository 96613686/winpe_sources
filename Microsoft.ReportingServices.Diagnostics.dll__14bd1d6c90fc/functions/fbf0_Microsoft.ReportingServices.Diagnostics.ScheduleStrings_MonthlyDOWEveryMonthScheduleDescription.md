# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MonthlyDOWEveryMonthScheduleDescription

- ea: `0xfbf0`
- end: `0xfbff`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MonthlyDOWEveryMonthScheduleDescription`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f50`

## string_xrefs

- `0xfbf0`: `MonthlyDOWEveryMonthScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfbf0  ldstr    aMonthlydowever// "MonthlyDOWEveryMonthScheduleDescription"
0xfbf5  ldarg.0
0xfbf6  ldarg.1
0xfbf7  ldarg.2
0xfbf8  ldarg.3
0xfbf9  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xfbfe  ret
```
