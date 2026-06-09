# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::DailyScheduleDescription

- ea: `0xc470`
- end: `0xc47d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::DailyScheduleDescription`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbdf0`

## callees

- `0x10c00`

## string_xrefs

- `0xc470`: `DailyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc470  ldstr    aDailyscheduled// "DailyScheduleDescription"
0xc475  ldarg.0
0xc476  ldarg.1
0xc477  call     string Keys::GetString(string key, object arg0, object arg1)
0xc47c  ret
```
