# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorThreadToken

- ea: `0x3da0`
- end: `0x3dab`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorThreadToken`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x4280`

## string_xrefs

- `0x3da0`: `ErrorThreadToken`

## pseudocode

```c

```

## disassembly

```asm
0x3da0  ldstr    aErrorthreadtok// "ErrorThreadToken"
0x3da5  call     string Keys::GetString(string key)
0x3daa  ret
```
