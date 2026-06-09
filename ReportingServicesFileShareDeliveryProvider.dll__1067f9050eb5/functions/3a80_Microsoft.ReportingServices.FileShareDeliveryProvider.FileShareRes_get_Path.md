# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Path

- ea: `0x3a80`
- end: `0x3a8b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_Path`
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
0x3a80  ldstr    aPath_0// "Path"
0x3a85  call     string Keys::GetString(string key)
0x3a8a  ret
```
