# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_AutoIncrement

- ea: `0x3b20`
- end: `0x3b2b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_AutoIncrement`
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
0x3b20  ldstr    aAutoincrement// "AutoIncrement"
0x3b25  call     string Keys::GetString(string key)
0x3b2a  ret
```
