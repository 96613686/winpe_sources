# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadConfigurationFile

- ea: `0x8c60`
- end: `0x8c6b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadConfigurationFile`
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

- `0x8c60`: `ErrorCodes_BadConfigurationFile`

## pseudocode

```c

```

## disassembly

```asm
0x8c60  ldstr    aErrorcodesBadc_0// "ErrorCodes_BadConfigurationFile"
0x8c65  call     string Keys::GetString(string key)
0x8c6a  ret
```
