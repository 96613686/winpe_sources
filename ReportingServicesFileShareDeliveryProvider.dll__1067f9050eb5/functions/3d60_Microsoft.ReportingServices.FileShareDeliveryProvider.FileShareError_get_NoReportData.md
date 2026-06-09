# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoReportData

- ea: `0x3d60`
- end: `0x3d6b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoReportData`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3d60  ldstr    aNoreportdata// "NoReportData"
0x3d65  call     string Keys::GetString(string key)
0x3d6a  ret
```
