# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileShareAccount

- ea: `0x3dc0`
- end: `0x3dcb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileShareAccount`
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
0x3dc0  ldstr    aNofileshareacc// "NoFileShareAccount"
0x3dc5  call     string Keys::GetString(string key)
0x3dca  ret
```
