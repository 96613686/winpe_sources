# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsURLAlreadyReserved

- ea: `0x8d90`
- end: `0x8d9b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsURLAlreadyReserved`
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

- `0x8d90`: `ErrorCodes_RsURLAlreadyReserved`

## pseudocode

```c

```

## disassembly

```asm
0x8d90  ldstr    aErrorcodesRsur_0// "ErrorCodes_RsURLAlreadyReserved"
0x8d95  call     string Keys::GetString(string key)
0x8d9a  ret
```
