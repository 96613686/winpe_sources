# SystemSettings::WorkAccess::CEnrollmentHelper::CheckAadEnrollmentTokenEx(HWND__ *,bool,ushort * *)

- ea: `0x180045cfc`
- end: `0x180045f8b`
- name: `?CheckAadEnrollmentTokenEx@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJPEAUHWND__@@_NPEAPEAG@Z`
- size: `655`
- prototype: `__int64 __fastcall(HWND, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002454c`

## callees

- `0x180002a60`
- `0x18000526c`
- `0x1800058fc`
- `0x1800069c4`
- `0x1800096ec`
- `0x18004566c`
- `0x180045cfc`
- `0x18004aff0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045d5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045ef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045d5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045d8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045ef2`
- `dmEnrollEngine!GetEnrollmentTenantID` at `0x180045dec`
- `dmEnrollEngine!GetEnrollmentTenantID` at `0x180045e7d`
- `dmEnrollEngine!GetEnrollmentTenantID` at `0x180045dec`
- `dmEnrollEngine!GetEnrollmentTenantID` at `0x180045e7d`
- `DMCmnUtils!DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery` at `0x180045ed5`
- `DMCmnUtils!DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery` at `0x180045f15`
- `DMCmnUtils!DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery` at `0x180045ed5`
- `DMCmnUtils!DmGetAadDeviceMdmEnrollmentResourceUrlForRecovery` at `0x180045f15`
- `RPCRT4!UuidFromStringW` at `0x180045d6f`
- `RPCRT4!UuidFromStringW` at `0x180045d9f`
- `RPCRT4!UuidFromStringW` at `0x180045e21`
- `RPCRT4!UuidFromStringW` at `0x180045d6f`
- `RPCRT4!UuidFromStringW` at `0x180045d9f`
- `RPCRT4!UuidFromStringW` at `0x180045e21`

## string_xrefs

- `0x180045f2c`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c

```
