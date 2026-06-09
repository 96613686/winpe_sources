# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_UNCPathNotValid

- ea: `0x3cf0`
- end: `0x3cfb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_UNCPathNotValid`
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

## string_xrefs

- `0x3cf0`: `UNCPathNotValid`

## pseudocode

```c

```

## disassembly

```asm
0x3cf0  ldstr    aUncpathnotvali// "UNCPathNotValid"
0x3cf5  call     string Keys::GetString(string key)
0x3cfa  ret
```
