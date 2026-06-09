# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsDeliveryExtensionNotFound

- ea: `0x8dc0`
- end: `0x8dcb`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsDeliveryExtensionNotFound`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8dc0`: `ErrorCodes_RsDeliveryExtensionNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x8dc0  ldstr    aErrorcodesRsde// "ErrorCodes_RsDeliveryExtensionNotFound"
0x8dc5  call     string Keys::GetString(string key)
0x8dca  ret
```
