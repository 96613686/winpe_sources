# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_EmptyPath

- ea: `0x3ce0`
- end: `0x3ceb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_EmptyPath`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x4280`

## string_xrefs

- `0x3ce0`: `EmptyPath`

## pseudocode

```c

```

## disassembly

```asm
0x3ce0  ldstr    aEmptypath// "EmptyPath"
0x3ce5  call     string Keys::GetString(string key)
0x3cea  ret
```
