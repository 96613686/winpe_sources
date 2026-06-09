# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Password

- ea: `0x3ae0`
- end: `0x3aeb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Password`
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
0x3ae0  ldstr    aPassword_0// "Password"
0x3ae5  call     string Keys::GetString(string key)
0x3aea  ret
```
