# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::WeeklyWithIntervalScheduleDescription

- ea: `0xc4b0`
- end: `0xc4c4`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::WeeklyWithIntervalScheduleDescription`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe30`

## callees

- `0x10c40`

## string_xrefs

- `0xc4b0`: `WeeklyWithIntervalScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc4b0  ldstr    aWeeklywithinte// "WeeklyWithIntervalScheduleDescription"
0xc4b5  ldarg.0
0xc4b6  ldarg.1
0xc4b7  ldarg.2
0xc4b8  box      [mscorlib]System.Int64
0xc4bd  ldarg.3
0xc4be  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xc4c3  ret
```
