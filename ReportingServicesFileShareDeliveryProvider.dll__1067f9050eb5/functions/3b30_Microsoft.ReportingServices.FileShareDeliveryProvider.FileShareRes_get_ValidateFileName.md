# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ValidateFileName

- ea: `0x3b30`
- end: `0x3b3b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_ValidateFileName`
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
0x3b30  ldstr    aValidatefilena// "ValidateFileName"
0x3b35  call     string Keys::GetString(string key)
0x3b3a  ret
```
