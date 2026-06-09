# CUtils::CreateAdminSid(void * *)

- ea: `0x18001f948`
- end: `0x18001f980`
- name: `?CreateAdminSid@CUtils@@SAJPEAPEAX@Z`
- size: `56`
- prototype: `signed int __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180020acc`
- `0x18005aff0`

## callees

- `0x18001f948`
- `0x1800268d0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001f957`
- `ntdll!RtlNtStatusToDosError` at `0x18001f957`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f95f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f95f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f965`

## pseudocode

```c

```
