# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_SecurityCredentials

- ea: `0x3aa0`
- end: `0x3aab`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_SecurityCredentials`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`
- `0x3390`

## callees

- `0x41a0`

## string_xrefs

- `0x3aa0`: `SecurityCredentials`

## pseudocode

```c

```

## disassembly

```asm
0x3aa0  ldstr    aSecuritycreden// "SecurityCredentials"
0x3aa5  call     string Keys::GetString(string key)
0x3aaa  ret
```
