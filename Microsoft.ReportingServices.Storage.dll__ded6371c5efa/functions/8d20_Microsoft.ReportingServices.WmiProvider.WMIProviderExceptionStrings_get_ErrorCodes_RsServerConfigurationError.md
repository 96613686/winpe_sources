# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsServerConfigurationError

- ea: `0x8d20`
- end: `0x8d2b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_RsServerConfigurationError`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x86b0`

## callees

- `0x99b0`

## string_xrefs

- `0x8d20`: `ErrorCodes_RsServerConfigurationError`

## pseudocode

```c

```

## disassembly

```asm
0x8d20  ldstr    aErrorcodesRsse// "ErrorCodes_RsServerConfigurationError"
0x8d25  call     string Keys::GetString(string key)
0x8d2a  ret
```
