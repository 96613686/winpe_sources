# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPassword

- ea: `0x3ca0`
- end: `0x3cab`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPassword`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`
- `0x28d0`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3ca0  ldstr    aNopassword// "NoPassword"
0x3ca5  call     string Keys::GetString(string key)
0x3caa  ret
```
