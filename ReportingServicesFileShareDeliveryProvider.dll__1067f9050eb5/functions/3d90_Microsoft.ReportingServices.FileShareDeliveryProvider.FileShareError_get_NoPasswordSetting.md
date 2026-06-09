# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPasswordSetting

- ea: `0x3d90`
- end: `0x3d9b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPasswordSetting`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3d90  ldstr    aNopasswordsett// "NoPasswordSetting"
0x3d95  call     string Keys::GetString(string key)
0x3d9a  ret
```
