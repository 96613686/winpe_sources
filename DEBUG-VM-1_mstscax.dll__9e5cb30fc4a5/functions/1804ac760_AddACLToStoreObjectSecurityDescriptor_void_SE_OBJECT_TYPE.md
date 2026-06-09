# AddACLToStoreObjectSecurityDescriptor(void *,_SE_OBJECT_TYPE)

- ea: `0x1804ac760`
- end: `0x1804acb70`
- name: `?AddACLToStoreObjectSecurityDescriptor@@YAHPEAXW4_SE_OBJECT_TYPE@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(void *, enum _SE_OBJECT_TYPE)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1804acc58`

## callees

- `0x1804ac760`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1804ac7d9`
- `KERNEL32!LoadLibraryW` at `0x1804ac7d9`
- `KERNEL32!OutputDebugStringW` at `0x1804aca85`
- `KERNEL32!OutputDebugStringW` at `0x1804aca85`
- `KERNEL32!LocalFree` at `0x1804acb34`
- `KERNEL32!LocalFree` at `0x1804acb34`
- `KERNEL32!GetProcAddress` at `0x1804ac7fa`
- `KERNEL32!GetProcAddress` at `0x1804ac816`
- `KERNEL32!GetProcAddress` at `0x1804aca70`
- `KERNEL32!GetProcAddress` at `0x1804acac7`
- `KERNEL32!GetProcAddress` at `0x1804ac7fa`
- `KERNEL32!GetProcAddress` at `0x1804ac816`
- `KERNEL32!GetProcAddress` at `0x1804aca70`
- `KERNEL32!GetProcAddress` at `0x1804acac7`
- `KERNEL32!FreeLibrary` at `0x1804acb3d`
- `KERNEL32!FreeLibrary` at `0x1804acb3d`

## string_xrefs

- `0x1804ac7a2`: `advapi32.dll`
- `0x1804acabd`: `FreeSid`
- `0x1804aca7e`: `AddSidToObjectsSecurityDescriptor: Can't get proc SetSecurityInfo`
- `0x1804aca66`: `SetSecurityInfo`
- `0x1804ac80c`: `SetEntriesInAclW`
- `0x1804ac7eb`: `AllocateAndInitializeSid`

## pseudocode

```c

```
