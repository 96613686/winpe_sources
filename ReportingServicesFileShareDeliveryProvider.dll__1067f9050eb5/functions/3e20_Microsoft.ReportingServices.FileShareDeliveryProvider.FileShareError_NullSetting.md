# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NullSetting

- ea: `0x3e20`
- end: `0x3e2c`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NullSetting`
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
0x3e20  ldstr    aNullsetting// "NullSetting"
0x3e25  ldarg.0
0x3e26  call     string Keys::GetString(string key, object arg0)
0x3e2b  ret
```
