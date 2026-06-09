# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyScheduleDescription

- ea: `0xfb80`
- end: `0xfb8e`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyScheduleDescription`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f30`

## string_xrefs

- `0xfb80`: `WeeklyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfb80  ldstr    aWeeklyschedule// "WeeklyScheduleDescription"
0xfb85  ldarg.0
0xfb86  ldarg.1
0xfb87  ldarg.2
0xfb88  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0xfb8d  ret
```
