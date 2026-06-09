# AddUserToHandle(void *,void *,ulong)

- ea: `0x1803ea070`
- end: `0x1803ea292`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `546`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803ea298`

## callees

- `0x1800432f0`
- `0x1800c2ec0`
- `0x18034f504`
- `0x1803a4cb0`
- `0x1803ea070`
- `0x1803eaa0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803ea0fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803ea0fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea0ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea1dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea231`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea252`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea0ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea1dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea231`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803ea252`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803ea1ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803ea23f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803ea260`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803ea1ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803ea23f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803ea260`
- `ntdll!NtSetSecurityObject` at `0x1803ea204`
- `ntdll!NtSetSecurityObject` at `0x1803ea204`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1803ea169`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1803ea169`
- `ntdll!NtQuerySecurityObject` at `0x1803ea0b4`
- `ntdll!NtQuerySecurityObject` at `0x1803ea140`
- `ntdll!NtQuerySecurityObject` at `0x1803ea0b4`
- `ntdll!NtQuerySecurityObject` at `0x1803ea140`

## string_xrefs

- `0x1803ea0c9`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803ea10c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803ea17c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803ea1bb`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803ea212`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c

```
