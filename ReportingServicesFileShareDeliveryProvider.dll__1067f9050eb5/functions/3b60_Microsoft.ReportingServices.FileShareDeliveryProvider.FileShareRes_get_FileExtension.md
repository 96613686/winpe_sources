# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtension

- ea: `0x3b60`
- end: `0x3b6b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtension`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x41a0`

## string_xrefs

- `0x3b60`: `FileExtension`

## pseudocode

```c

```

## disassembly

```asm
0x3b60  ldstr    aFileextension// "FileExtension"
0x3b65  call     string Keys::GetString(string key)
0x3b6a  ret
```
