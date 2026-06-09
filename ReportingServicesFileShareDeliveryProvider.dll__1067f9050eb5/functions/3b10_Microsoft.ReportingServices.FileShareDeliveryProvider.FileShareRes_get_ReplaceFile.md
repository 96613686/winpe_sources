# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReplaceFile

- ea: `0x3b10`
- end: `0x3b1b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReplaceFile`
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

- `0x3b10`: `ReplaceFile`

## pseudocode

```c

```

## disassembly

```asm
0x3b10  ldstr    aReplacefile// "ReplaceFile"
0x3b15  call     string Keys::GetString(string key)
0x3b1a  ret
```
