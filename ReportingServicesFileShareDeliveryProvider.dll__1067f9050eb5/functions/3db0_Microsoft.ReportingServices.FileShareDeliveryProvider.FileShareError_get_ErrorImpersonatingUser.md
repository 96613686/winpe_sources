# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorImpersonatingUser

- ea: `0x3db0`
- end: `0x3dbb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_ErrorImpersonatingUser`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b70`

## callees

- `0x4280`

## string_xrefs

- `0x3db0`: `ErrorImpersonatingUser`

## pseudocode

```c

```

## disassembly

```asm
0x3db0  ldstr    aErrorimpersona// "ErrorImpersonatingUser"
0x3db5  call     string Keys::GetString(string key)
0x3dba  ret
```
