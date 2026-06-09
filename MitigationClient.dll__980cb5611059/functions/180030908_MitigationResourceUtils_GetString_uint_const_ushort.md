# MitigationResourceUtils::GetString(uint const &,ushort * *)

- ea: `0x180030908`
- end: `0x180030a93`
- name: `?GetString@MitigationResourceUtils@@SAJAEBIPEAPEAG@Z`
- size: `395`
- prototype: `__int64 __fastcall(const unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x1800358e8`

## callees

- `0x18000a6e0`
- `0x18001206c`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800198b0`
- `0x18002407c`
- `0x1800240b8`
- `0x180030544`
- `0x1800307fc`
- `0x180030908`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003093b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003093b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030949`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180030990`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180030990`

## string_xrefs

- `0x180030934`: `mitigationclient.dll`

## pseudocode

```c

```
