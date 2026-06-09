# BfspSetFileDirectorySecurityDescriptor

- ea: `0x18004d3e0`
- end: `0x18004d4f8`
- name: `BfspSetFileDirectorySecurityDescriptor`
- size: `280`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180049234`
- `0x18004a678`

## callees

- `0x180008724`
- `0x180047280`
- `0x18004cdd4`
- `0x18004d214`
- `0x18004d3e0`
- `0x18004d500`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d4c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d4c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d403`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d4b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d403`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d4b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d419`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d419`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d4dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d4d1`

## string_xrefs

- `0x18004d4a1`: `BfspSetSecurityDescriptor(%s) failed! Last Error = %#x`

## pseudocode

```c

```
