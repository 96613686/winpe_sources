# Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetSid(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,ushort * *)

- ea: `0x180034000`
- end: `0x1800340e6`
- name: `?GetSid@AssignedAccessUserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAUIAssignedAccessUserInfo@234@PEAPEAG@Z`
- size: `230`
- prototype: `static int(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180032138`
- `0x180036308`
- `0x180037bb0`
- `0x180037cf0`
- `0x180038050`
- `0x18003bd70`

## callees

- `0x18000b6b4`
- `0x1800224c4`
- `0x180022d00`
- `0x1800271e4`
- `0x18002901c`
- `0x180034000`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034096`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034096`

## string_xrefs

- `0x180034027`: `onecoreuap\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x18003407c`: `onecoreuap\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`

## pseudocode

```c

```
