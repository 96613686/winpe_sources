# EfspTryAddUserProfileToCache(_EFS_USER_INFO *)

- ea: `0x180024bc4`
- end: `0x180024cf4`
- name: `?EfspTryAddUserProfileToCache@@YAKPEAU_EFS_USER_INFO@@@Z`
- size: `304`
- prototype: `unsigned int __fastcall(struct _EFS_USER_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800257b0`

## callees

- `0x180024960`
- `0x180024bc4`
- `0x180035db8`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024bf0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024bf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024bde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024bde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cd4`
- `ntdll!RtlLeaveCriticalSection` at `0x180024ce1`
- `ntdll!RtlLeaveCriticalSection` at `0x180024ce1`
- `ntdll!RtlEnterCriticalSection` at `0x180024bd8`
- `ntdll!RtlEnterCriticalSection` at `0x180024bd8`

## pseudocode

```c

```
