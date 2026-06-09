# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileName

- ea: `0x3a70`
- end: `0x3a7b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_FileName`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3a70  ldstr    aFilename_0// "FileName"
0x3a75  call     string Keys::GetString(string key)
0x3a7a  ret
```
