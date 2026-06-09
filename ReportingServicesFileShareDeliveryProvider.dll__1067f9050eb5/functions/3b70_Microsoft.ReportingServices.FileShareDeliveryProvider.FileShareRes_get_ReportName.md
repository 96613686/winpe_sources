# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReportName

- ea: `0x3b70`
- end: `0x3b7b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReportName`
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
0x3b70  ldstr    aReportname// "ReportName"
0x3b75  call     string Keys::GetString(string key)
0x3b7a  ret
```
