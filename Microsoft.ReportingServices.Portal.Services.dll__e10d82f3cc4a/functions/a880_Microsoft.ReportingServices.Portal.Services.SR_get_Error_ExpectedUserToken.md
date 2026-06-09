# Microsoft.ReportingServices.Portal.Services.SR::get_Error_ExpectedUserToken

- ea: `0xa880`
- end: `0xa88b`
- name: `Microsoft.ReportingServices.Portal.Services.SR::get_Error_ExpectedUserToken`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20b30`

## string_xrefs

- `0xa880`: `Error_ExpectedUserToken`

## pseudocode

```c

```

## disassembly

```asm
0xa880  ldstr    aErrorExpectedu// "Error_ExpectedUserToken"
0xa885  call     string Keys::GetString(string key)
0xa88a  ret
```
