# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_GenericError

- ea: `0x3d20`
- end: `0x3d2b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_GenericError`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3d20  ldstr    aGenericerror// "GenericError"
0x3d25  call     string Keys::GetString(string key)
0x3d2a  ret
```
