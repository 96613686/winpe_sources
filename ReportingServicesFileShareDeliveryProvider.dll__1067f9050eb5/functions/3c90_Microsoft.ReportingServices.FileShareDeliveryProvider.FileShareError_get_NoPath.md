# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPath

- ea: `0x3c90`
- end: `0x3c9b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPath`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`

## callees

- `0x4280`

## string_xrefs

- `0x3c90`: `NoPath`

## pseudocode

```c

```

## disassembly

```asm
0x3c90  ldstr    aNopath// "NoPath"
0x3c95  call     string Keys::GetString(string key)
0x3c9a  ret
```
