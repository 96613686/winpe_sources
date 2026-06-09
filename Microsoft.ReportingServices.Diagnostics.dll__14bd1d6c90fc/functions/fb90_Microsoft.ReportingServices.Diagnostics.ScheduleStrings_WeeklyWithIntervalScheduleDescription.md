# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyWithIntervalScheduleDescription

- ea: `0xfb90`
- end: `0xfba4`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyWithIntervalScheduleDescription`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f50`

## string_xrefs

- `0xfb90`: `WeeklyWithIntervalScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfb90  ldstr    aWeeklywithinte// "WeeklyWithIntervalScheduleDescription"
0xfb95  ldarg.0
0xfb96  ldarg.1
0xfb97  ldarg.2
0xfb98  box      [mscorlib]System.Int64
0xfb9d  ldarg.3
0xfb9e  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xfba3  ret
```
