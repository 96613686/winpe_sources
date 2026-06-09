# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileExt

- ea: `0x3c70`
- end: `0x3c7b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileExt`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3c70  ldstr    aInvalidfileext// "InvalidFileExt"
0x3c75  call     string Keys::GetString(string key)
0x3c7a  ret
```
