# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UserName

- ea: `0x3ad0`
- end: `0x3adb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UserName`
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
0x3ad0  ldstr    aUsername_0// "UserName"
0x3ad5  call     string Keys::GetString(string key)
0x3ada  ret
```
