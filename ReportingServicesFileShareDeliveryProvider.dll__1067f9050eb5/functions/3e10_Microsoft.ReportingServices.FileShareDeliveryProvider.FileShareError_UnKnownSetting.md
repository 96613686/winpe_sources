# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::UnKnownSetting

- ea: `0x3e10`
- end: `0x3e1c`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::UnKnownSetting`
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
0x3e10  ldstr    aUnknownsetting// "UnKnownSetting"
0x3e15  ldarg.0
0x3e16  call     string Keys::GetString(string key, object arg0)
0x3e1b  ret
```
