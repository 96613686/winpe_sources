# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::OnceScheduleDescription

- ea: `0xc440`
- end: `0xc44d`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::OnceScheduleDescription`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd80`

## callees

- `0x10c00`

## string_xrefs

- `0xc440`: `OnceScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc440  ldstr    aOnceschedulede// "OnceScheduleDescription"
0xc445  ldarg.0
0xc446  ldarg.1
0xc447  call     string Keys::GetString(string key, object arg0, object arg1)
0xc44c  ret
```
