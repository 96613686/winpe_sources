# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_WebServiceAccountNotSet

- ea: `0x8b60`
- end: `0x8b6b`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_WebServiceAccountNotSet`
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

- `0x8b60`: `ErrorCodes_WebServiceAccountNotSet`

## pseudocode

```c

```

## disassembly

```asm
0x8b60  ldstr    aErrorcodesWebs// "ErrorCodes_WebServiceAccountNotSet"
0x8b65  call     string Keys::GetString(string key)
0x8b6a  ret
```
