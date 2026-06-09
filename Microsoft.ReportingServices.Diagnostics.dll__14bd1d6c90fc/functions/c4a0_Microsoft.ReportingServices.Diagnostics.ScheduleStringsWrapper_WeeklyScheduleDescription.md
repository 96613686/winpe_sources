# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::WeeklyScheduleDescription

- ea: `0xc4a0`
- end: `0xc4ae`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::WeeklyScheduleDescription`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe30`

## callees

- `0x10c20`

## string_xrefs

- `0xc4a0`: `WeeklyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc4a0  ldstr    aWeeklyschedule// "WeeklyScheduleDescription"
0xc4a5  ldarg.0
0xc4a6  ldarg.1
0xc4a7  ldarg.2
0xc4a8  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0xc4ad  ret
```
