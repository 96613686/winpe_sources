# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoUserNameSetting

- ea: `0x3d80`
- end: `0x3d8b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoUserNameSetting`
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
0x3d80  ldstr    aNousernamesett// "NoUserNameSetting"
0x3d85  call     string Keys::GetString(string key)
0x3d8a  ret
```
