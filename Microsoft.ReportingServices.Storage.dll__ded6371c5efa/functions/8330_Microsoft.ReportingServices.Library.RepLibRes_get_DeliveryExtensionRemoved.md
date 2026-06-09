# Microsoft.ReportingServices.Library.RepLibRes::get_DeliveryExtensionRemoved

- ea: `0x8330`
- end: `0x833b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_DeliveryExtensionRemoved`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x8330`: `DeliveryExtensionRemoved`

## pseudocode

```c

```

## disassembly

```asm
0x8330  ldstr    aDeliveryextens// "DeliveryExtensionRemoved"
0x8335  call     string Keys::GetString(string key)
0x833a  ret
```
