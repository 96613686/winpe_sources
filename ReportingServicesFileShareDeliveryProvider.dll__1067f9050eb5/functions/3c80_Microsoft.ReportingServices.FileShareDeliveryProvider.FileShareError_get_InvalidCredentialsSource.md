# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidCredentialsSource

- ea: `0x3c80`
- end: `0x3c8b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidCredentialsSource`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3c80  ldstr    aInvalidcredent// "InvalidCredentialsSource"
0x3c85  call     string Keys::GetString(string key)
0x3c8a  ret
```
