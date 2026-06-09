# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_PasswordSetting

- ea: `0x3bd0`
- end: `0x3bdb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_PasswordSetting`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa30`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3bd0  ldstr    aPasswordsettin// "PasswordSetting"
0x3bd5  call     string Keys::GetString(string key)
0x3bda  ret
```
