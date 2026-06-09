# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::RequiredSettingNotFound

- ea: `0x3e30`
- end: `0x3e3c`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::RequiredSettingNotFound`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`

## callees

- `0x42a0`

## pseudocode

```c

```

## disassembly

```asm
0x3e30  ldstr    aRequiredsettin// "RequiredSettingNotFound"
0x3e35  ldarg.0
0x3e36  call     string Keys::GetString(string key, object arg0)
0x3e3b  ret
```
