# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_True

- ea: `0x3b80`
- end: `0x3b8b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_True`
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
0x3b80  ldstr    aTrue_0// "True"
0x3b85  call     string Keys::GetString(string key)
0x3b8a  ret
```
