# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MonthlyDOWEveryMonthScheduleDescription

- ea: `0xc510`
- end: `0xc51f`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MonthlyDOWEveryMonthScheduleDescription`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbed0`

## callees

- `0x10c40`

## string_xrefs

- `0xc510`: `MonthlyDOWEveryMonthScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc510  ldstr    aMonthlydowever// "MonthlyDOWEveryMonthScheduleDescription"
0xc515  ldarg.0
0xc516  ldarg.1
0xc517  ldarg.2
0xc518  ldarg.3
0xc519  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xc51e  ret
```
