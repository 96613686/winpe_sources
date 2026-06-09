# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::OnceScheduleDescription

- ea: `0xfb20`
- end: `0xfb2d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::OnceScheduleDescription`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f10`

## string_xrefs

- `0xfb20`: `OnceScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfb20  ldstr    aOnceschedulede// "OnceScheduleDescription"
0xfb25  ldarg.0
0xfb26  ldarg.1
0xfb27  call     string Keys::GetString(string key, object arg0, object arg1)
0xfb2c  ret
```
