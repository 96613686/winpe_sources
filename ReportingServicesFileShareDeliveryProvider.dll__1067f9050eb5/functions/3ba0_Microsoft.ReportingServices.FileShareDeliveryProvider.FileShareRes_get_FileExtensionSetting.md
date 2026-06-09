# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtensionSetting

- ea: `0x3ba0`
- end: `0x3bab`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileExtensionSetting`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xa30`

## callees

- `0x41a0`

## string_xrefs

- `0x3ba0`: `FileExtensionSetting`

## pseudocode

```c

```

## disassembly

```asm
0x3ba0  ldstr    aFileextensions// "FileExtensionSetting"
0x3ba5  call     string Keys::GetString(string key)
0x3baa  ret
```
