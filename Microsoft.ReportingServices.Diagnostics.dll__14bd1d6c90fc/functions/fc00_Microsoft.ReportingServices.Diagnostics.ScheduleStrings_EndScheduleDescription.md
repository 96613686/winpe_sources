# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::EndScheduleDescription

- ea: `0xfc00`
- end: `0xfc0c`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::EndScheduleDescription`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10ef0`

## string_xrefs

- `0xfc00`: `EndScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfc00  ldstr    aEndscheduledes// "EndScheduleDescription"
0xfc05  ldarg.0
0xfc06  call     string Keys::GetString(string key, object arg0)
0xfc0b  ret
```
