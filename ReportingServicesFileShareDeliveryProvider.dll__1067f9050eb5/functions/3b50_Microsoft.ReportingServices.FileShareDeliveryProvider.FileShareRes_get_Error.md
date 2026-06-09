# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Error

- ea: `0x3b50`
- end: `0x3b5b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Error`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3b50  ldstr    aError// "Error"
0x3b55  call     string Keys::GetString(string key)
0x3b5a  ret
```
