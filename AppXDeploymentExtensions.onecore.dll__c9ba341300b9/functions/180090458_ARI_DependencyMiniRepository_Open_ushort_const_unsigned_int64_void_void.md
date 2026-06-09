# ARI::DependencyMiniRepository::Open(ushort const *,unsigned __int64 *,void * *,void * *)

- ea: `0x180090458`
- end: `0x180090609`
- name: `?Open@DependencyMiniRepository@ARI@@YAJPEBGPEA_KPEAPEAX2@Z`
- size: `433`
- prototype: `__int64 __fastcall(struct _EVENT_DATA_DESCRIPTOR *this, const unsigned __int16 *, unsigned __int64 *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800d12e8`

## callees

- `0x180090458`
- `0x180127158`
- `0x1801281d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800904aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800904aa`
- `ntdll!NtMapViewOfSection` at `0x18009055e`
- `ntdll!NtMapViewOfSection` at `0x18009055e`
- `ntdll!NtUnmapViewOfSection` at `0x1800905c5`
- `ntdll!NtUnmapViewOfSection` at `0x1800905c5`
- `ntdll!NtClose` at `0x1800904fb`
- `ntdll!NtClose` at `0x18009056e`
- `ntdll!NtClose` at `0x18009057f`
- `ntdll!NtClose` at `0x1800905d4`
- `ntdll!NtClose` at `0x1800904fb`
- `ntdll!NtClose` at `0x18009056e`
- `ntdll!NtClose` at `0x18009057f`
- `ntdll!NtClose` at `0x1800905d4`
- `ntdll!NtCreateSection` at `0x1800904f0`
- `ntdll!NtCreateSection` at `0x1800904f0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180090507`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180090507`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009049b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009049b`

## pseudocode

```c

```
