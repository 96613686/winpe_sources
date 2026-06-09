# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_UnauthorizedAccessError

- ea: `0x3d10`
- end: `0x3d1b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_UnauthorizedAccessError`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4280`

## string_xrefs

- `0x3d10`: `UnauthorizedAccessError`

## pseudocode

```c

```

## disassembly

```asm
0x3d10  ldstr    aUnauthorizedac// "UnauthorizedAccessError"
0x3d15  call     string Keys::GetString(string key)
0x3d1a  ret
```
