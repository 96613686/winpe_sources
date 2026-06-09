# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsUrlAlreadyReservedDifferentName

- ea: `0x8d30`
- end: `0x8d3b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsUrlAlreadyReservedDifferentName`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8d30`: `ErrorCodes_RsUrlAlreadyReservedDifferentName`

## pseudocode

```c

```

## disassembly

```asm
0x8d30  ldstr    aErrorcodesRsur// "ErrorCodes_RsUrlAlreadyReservedDifferen"...
0x8d35  call     string Keys::GetString(string key)
0x8d3a  ret
```
