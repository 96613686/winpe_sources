# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyScheduleDescription

- ea: `0x10570`
- end: `0x1057d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyScheduleDescription`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x16480`

## string_xrefs

- `0x10570`: `DailyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x10570  ldstr    aDailyscheduled// "DailyScheduleDescription"
0x10575  ldarg.0
0x10576  ldarg.1
0x10577  call     string Keys::GetString(string key, object arg0, object arg1)
0x1057c  ret
```
