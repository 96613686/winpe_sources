# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::OnceScheduleDescription

- ea: `0x10540`
- end: `0x1054d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::OnceScheduleDescription`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x16480`

## string_xrefs

- `0x10540`: `OnceScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x10540  ldstr    aOnceschedulede// "OnceScheduleDescription"
0x10545  ldarg.0
0x10546  ldarg.1
0x10547  call     string Keys::GetString(string key, object arg0, object arg1)
0x1054c  ret
```
