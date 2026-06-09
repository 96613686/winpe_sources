# Microsoft.ReportingServices.Portal.Services.SR::get_Error_AccessDenied

- ea: `0xa860`
- end: `0xa86b`
- name: `Microsoft.ReportingServices.Portal.Services.SR::get_Error_AccessDenied`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20b30`

## string_xrefs

- `0xa860`: `Error_AccessDenied`

## pseudocode

```c

```

## disassembly

```asm
0xa860  ldstr    aErrorAccessden// "Error_AccessDenied"
0xa865  call     string Keys::GetString(string key)
0xa86a  ret
```
