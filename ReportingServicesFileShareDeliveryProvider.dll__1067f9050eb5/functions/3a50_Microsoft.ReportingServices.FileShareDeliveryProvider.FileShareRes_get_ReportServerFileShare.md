# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReportServerFileShare

- ea: `0x3a50`
- end: `0x3a5b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReportServerFileShare`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa20`
- `0x22b0`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3a50  ldstr    aReportserverfi// "ReportServerFileShare"
0x3a55  call     string Keys::GetString(string key)
0x3a5a  ret
```
