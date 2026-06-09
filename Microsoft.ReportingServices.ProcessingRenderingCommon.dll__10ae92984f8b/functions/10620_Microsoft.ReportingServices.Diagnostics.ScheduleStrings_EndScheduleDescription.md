# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::EndScheduleDescription

- ea: `0x10620`
- end: `0x1062c`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::EndScheduleDescription`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x16460`

## string_xrefs

- `0x10620`: `EndScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x10620  ldstr    aEndscheduledes// "EndScheduleDescription"
0x10625  ldarg.0
0x10626  call     string Keys::GetString(string key, object arg0)
0x1062b  ret
```
