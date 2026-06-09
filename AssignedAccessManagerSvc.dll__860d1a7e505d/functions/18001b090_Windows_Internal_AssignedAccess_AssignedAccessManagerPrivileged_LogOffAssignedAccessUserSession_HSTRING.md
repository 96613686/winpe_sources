# Windows::Internal::AssignedAccess::AssignedAccessManagerPrivileged::LogOffAssignedAccessUserSession(HSTRING__ *)

- ea: `0x18001b090`
- end: `0x18001b1d2`
- name: `?LogOffAssignedAccessUserSession@AssignedAccessManagerPrivileged@AssignedAccess@Internal@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AssignedAccessManagerPrivileged *this, HSTRING)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180006640`
- `0x180008e90`
- `0x18000b694`
- `0x18000b6b4`
- `0x180013fac`
- `0x180015450`
- `0x18001b090`
- `0x18001f19c`
- `0x18001f2b0`
- `0x18004f4d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b10c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b10c`
- `ntdll!RtlIsMultiSessionSku` at `0x18001b0e3`
- `ntdll!RtlIsMultiSessionSku` at `0x18001b0e3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x18001b16a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x18001b16a`

## string_xrefs

- `0x18001b13a`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccessmanagerprivileged.cpp`
- `0x18001b17c`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccessmanagerprivileged.cpp`
- `0x18001b0ae`: `AAManagerPrivilegedLogOffAssignedAccessUserSession`

## pseudocode

```c

```
