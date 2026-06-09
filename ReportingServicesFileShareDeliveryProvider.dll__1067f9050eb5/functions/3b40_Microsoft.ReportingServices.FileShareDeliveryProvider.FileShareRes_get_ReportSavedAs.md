# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReportSavedAs

- ea: `0x3b40`
- end: `0x3b4b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ReportSavedAs`
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
0x3b40  ldstr    aReportsavedas// "ReportSavedAs"
0x3b45  call     string Keys::GetString(string key)
0x3b4a  ret
```
