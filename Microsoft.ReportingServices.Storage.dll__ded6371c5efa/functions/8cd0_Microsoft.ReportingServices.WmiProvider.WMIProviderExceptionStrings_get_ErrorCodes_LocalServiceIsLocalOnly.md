# Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_LocalServiceIsLocalOnly

- ea: `0x8cd0`
- end: `0x8cdb`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ErrorCodes_LocalServiceIsLocalOnly`
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

- `0x8cd0`: `ErrorCodes_LocalServiceIsLocalOnly`

## pseudocode

```c

```

## disassembly

```asm
0x8cd0  ldstr    aErrorcodesLoca// "ErrorCodes_LocalServiceIsLocalOnly"
0x8cd5  call     string Keys::GetString(string key)
0x8cda  ret
```
