# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyScheduleDescription

- ea: `0xfb50`
- end: `0xfb5d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyScheduleDescription`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f10`

## string_xrefs

- `0xfb50`: `DailyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfb50  ldstr    aDailyscheduled// "DailyScheduleDescription"
0xfb55  ldarg.0
0xfb56  ldarg.1
0xfb57  call     string Keys::GetString(string key, object arg0, object arg1)
0xfb5c  ret
```
