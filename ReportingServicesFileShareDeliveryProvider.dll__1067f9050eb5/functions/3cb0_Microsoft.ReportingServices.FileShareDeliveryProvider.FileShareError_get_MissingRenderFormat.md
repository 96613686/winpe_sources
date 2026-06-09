# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_MissingRenderFormat

- ea: `0x3cb0`
- end: `0x3cbb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_MissingRenderFormat`
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
0x3cb0  ldstr    aMissingrenderf// "MissingRenderFormat"
0x3cb5  call     string Keys::GetString(string key)
0x3cba  ret
```
