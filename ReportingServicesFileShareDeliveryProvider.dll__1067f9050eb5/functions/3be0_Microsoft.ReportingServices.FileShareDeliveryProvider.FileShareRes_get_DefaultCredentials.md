# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_DefaultCredentials

- ea: `0x3be0`
- end: `0x3beb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_DefaultCredentials`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa30`

## callees

- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x3be0  ldstr    aDefaultcredent_0// "DefaultCredentials"
0x3be5  call     string Keys::GetString(string key)
0x3bea  ret
```
