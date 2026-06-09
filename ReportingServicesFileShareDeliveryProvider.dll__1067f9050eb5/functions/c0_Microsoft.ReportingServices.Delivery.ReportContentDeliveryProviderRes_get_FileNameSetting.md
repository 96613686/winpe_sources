# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_FileNameSetting

- ea: `0xc0`
- end: `0xcb`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_FileNameSetting`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x460`
- `0xa30`

## callees

- `0x3ed0`

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldstr    aFilenamesettin// "FileNameSetting"
0xc5  call     string Keys::GetString(string key)
0xca  ret
```
