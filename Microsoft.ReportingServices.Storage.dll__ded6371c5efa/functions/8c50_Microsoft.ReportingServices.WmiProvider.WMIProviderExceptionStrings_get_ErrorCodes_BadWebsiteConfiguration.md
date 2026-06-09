# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadWebsiteConfiguration

- ea: `0x8c50`
- end: `0x8c5b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_BadWebsiteConfiguration`
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

- `0x8c50`: `ErrorCodes_BadWebsiteConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x8c50  ldstr    aErrorcodesBadw// "ErrorCodes_BadWebsiteConfiguration"
0x8c55  call     string Keys::GetString(string key)
0x8c5a  ret
```
