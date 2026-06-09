# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UsernameSetting

- ea: `0x3bc0`
- end: `0x3bcb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UsernameSetting`
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
0x3bc0  ldstr    aUsernamesettin// "UsernameSetting"
0x3bc5  call     string Keys::GetString(string key)
0x3bca  ret
```
