# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_WindowsCredentials

- ea: `0x3ac0`
- end: `0x3acb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_WindowsCredentials`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3390`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  ldstr    aWindowscredent// "WindowsCredentials"
0x3ac5  call     string Keys::GetString(string key)
0x3aca  ret
```
