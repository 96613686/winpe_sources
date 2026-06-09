# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyScheduleDescription

- ea: `0x105a0`
- end: `0x105ae`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyScheduleDescription`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x164a0`

## string_xrefs

- `0x105a0`: `WeeklyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x105a0  ldstr    aWeeklyschedule// "WeeklyScheduleDescription"
0x105a5  ldarg.0
0x105a6  ldarg.1
0x105a7  ldarg.2
0x105a8  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0x105ad  ret
```
