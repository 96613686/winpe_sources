# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription

- ea: `0xc520`
- end: `0xc52c`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::EndScheduleDescription`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd80`
- `0xbdb0`
- `0xbdf0`
- `0xbe30`
- `0xbe80`
- `0xbed0`

## callees

- `0x10be0`

## string_xrefs

- `0xc520`: `EndScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc520  ldstr    aEndscheduledes// "EndScheduleDescription"
0xc525  ldarg.0
0xc526  call     string Keys::GetString(string key, object arg0)
0xc52b  ret
```
