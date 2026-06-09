# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ReEnterPassword

- ea: `0x3cc0`
- end: `0x3ccb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ReEnterPassword`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3cc0  ldstr    aReenterpasswor// "ReEnterPassword"
0x3cc5  call     string Keys::GetString(string key)
0x3cca  ret
```
