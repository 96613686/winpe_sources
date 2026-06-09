# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_NotReplaceFile

- ea: `0x3b00`
- end: `0x3b0b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_NotReplaceFile`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x41a0`

## string_xrefs

- `0x3b00`: `NotReplaceFile`

## pseudocode

```c

```

## disassembly

```asm
0x3b00  ldstr    aNotreplacefile// "NotReplaceFile"
0x3b05  call     string Keys::GetString(string key)
0x3b0a  ret
```
