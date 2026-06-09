# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidUserNamePassword

- ea: `0x3d70`
- end: `0x3d7b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidUserNamePassword`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b70`

## callees

- `0x4280`

## pseudocode

```c

```

## disassembly

```asm
0x3d70  ldstr    aInvalidusernam// "InvalidUserNamePassword"
0x3d75  call     string Keys::GetString(string key)
0x3d7a  ret
```
