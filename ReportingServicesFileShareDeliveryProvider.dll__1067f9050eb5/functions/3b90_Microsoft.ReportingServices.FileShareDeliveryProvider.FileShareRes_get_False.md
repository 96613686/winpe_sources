# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_False

- ea: `0x3b90`
- end: `0x3b9b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_False`
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
0x3b90  ldstr    aFalse_0// "False"
0x3b95  call     string Keys::GetString(string key)
0x3b9a  ret
```
