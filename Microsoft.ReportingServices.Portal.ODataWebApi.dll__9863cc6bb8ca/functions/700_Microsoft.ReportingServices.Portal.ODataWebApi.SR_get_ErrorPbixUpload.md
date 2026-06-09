# Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ErrorPbixUpload

- ea: `0x700`
- end: `0x70b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ErrorPbixUpload`
- size: `11`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xce30`
- `0xcec0`
- `0xcf30`

## callees

- `0xd270`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldstr    aErrorpbixuploa// "ErrorPbixUpload"
0x705  call     string Keys::GetString(string key)
0x70a  ret
```
