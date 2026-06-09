# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ConfigurationFileNotFound

- ea: `0x8b80`
- end: `0x8b8b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_ConfigurationFileNotFound`
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

- `0x8b80`: `ErrorCodes_ConfigurationFileNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x8b80  ldstr    aErrorcodesConf// "ErrorCodes_ConfigurationFileNotFound"
0x8b85  call     string Keys::GetString(string key)
0x8b8a  ret
```
