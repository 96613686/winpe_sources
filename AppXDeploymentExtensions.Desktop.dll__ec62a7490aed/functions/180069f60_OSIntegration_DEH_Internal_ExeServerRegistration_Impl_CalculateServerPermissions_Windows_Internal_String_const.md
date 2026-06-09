# OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions(Windows::Internal::String const &)

- ea: `0x180069f60`
- end: `0x18006a318`
- name: `?CalculateServerPermissions@ExeServerRegistration_Impl@Internal@DEH@OSIntegration@@EEAAJAEBVString@2Windows@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *__hidden this, const struct Windows::Internal::String *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009dc0`
- `0x180015590`
- `0x180036e58`
- `0x18003dbd0`
- `0x180069f60`
- `0x18006a4c8`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800eb890`
- `0x18015c644`
- `0x18016b374`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180069faf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180069faf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a0be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a0be`
- `ntdll!RtlIsMultiSessionSku` at `0x18006a02b`
- `ntdll!RtlIsMultiSessionSku` at `0x18006a02b`

## string_xrefs

- `0x18006a232`: `securityDescriptorString.Concat(packageDaclString, &securityDescriptorString)`
- `0x18006a0f2`: `packageSidString.SetValueFromString(packageSid.GetRawBuffer(nullptr))`
- `0x18006a15d`: `packageDacl`
- `0x18006a1c1`: `StringCchPrintfW(packageDacl, length, comDACLFormat, packageSidString.GetChars())`
- `0x18006a268`: `securityDescriptorString.Concat(saclString, &securityDescriptorString)`
- `0x18006a06b`: `securityDescriptorString.Initialize(permissions)`
- `0x18006a00b`: `securityDescriptorString.Initialize(defaultAAAPermissionsBase)`
- `0x18006a2d5`: `SetRegistrationProperty(_properties.Permissions, securityDescriptorString.Get())`

## pseudocode

```c

```
