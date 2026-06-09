# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_CredentialSetting

- ea: `0x3bb0`
- end: `0x3bbb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareRes::get_CredentialSetting`
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
0x3bb0  ldstr    aCredentialsett// "CredentialSetting"
0x3bb5  call     string Keys::GetString(string key)
0x3bba  ret
```
