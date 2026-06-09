# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileName

- ea: `0x3c50`
- end: `0x3c5b`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileName`
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
0x3c50  ldstr    aNofilename// "NoFileName"
0x3c55  call     string Keys::GetString(string key)
0x3c5a  ret
```
