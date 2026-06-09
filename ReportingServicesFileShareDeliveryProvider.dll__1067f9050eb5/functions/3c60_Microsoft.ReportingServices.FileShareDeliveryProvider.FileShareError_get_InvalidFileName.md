# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileName

- ea: `0x3c60`
- end: `0x3c6b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileName`
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
0x3c60  ldstr    aInvalidfilenam// "InvalidFileName"
0x3c65  call     string Keys::GetString(string key)
0x3c6a  ret
```
