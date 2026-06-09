# Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ReportDocument_DeserializationFailed

- ea: `0xd20`
- end: `0xd2b`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.SR::get_ReportDocument_DeserializationFailed`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7a0`

## callees

- `0x2280`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldstr    aReportdocument// "ReportDocument_DeserializationFailed"
0xd25  call     string Keys::GetString(string key)
0xd2a  ret
```
