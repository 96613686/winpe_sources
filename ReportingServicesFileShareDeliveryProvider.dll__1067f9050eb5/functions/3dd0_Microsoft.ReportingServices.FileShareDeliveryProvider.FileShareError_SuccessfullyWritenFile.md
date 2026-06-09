# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::SuccessfullyWritenFile

- ea: `0x3dd0`
- end: `0x3ddd`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::SuccessfullyWritenFile`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1270`

## callees

- `0x42c0`

## string_xrefs

- `0x3dd0`: `SuccessfullyWritenFile`

## pseudocode

```c

```

## disassembly

```asm
0x3dd0  ldstr    aSuccessfullywr// "SuccessfullyWritenFile"
0x3dd5  ldarg.0
0x3dd6  ldarg.1
0x3dd7  call     string Keys::GetString(string key, object arg0, object arg1)
0x3ddc  ret
```
