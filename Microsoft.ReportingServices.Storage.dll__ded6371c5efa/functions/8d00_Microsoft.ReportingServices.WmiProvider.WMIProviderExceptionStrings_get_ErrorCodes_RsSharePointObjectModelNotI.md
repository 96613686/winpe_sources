# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsSharePointObjectModelNotInstalled

- ea: `0x8d00`
- end: `0x8d0b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsSharePointObjectModelNotInstalled`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8d00`: `ErrorCodes_RsSharePointObjectModelNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x8d00  ldstr    aErrorcodesRssh// "ErrorCodes_RsSharePointObjectModelNotIn"...
0x8d05  call     string Keys::GetString(string key)
0x8d0a  ret
```
