# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UseFileShareAccount

- ea: `0x3ab0`
- end: `0x3abb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_UseFileShareAccount`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3390`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3ab0  ldstr    aUsefileshareac// "UseFileShareAccount"
0x3ab5  call     string Keys::GetString(string key)
0x3aba  ret
```
