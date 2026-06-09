# OneCoreInfoGather::GetStorageHelper(wchar_t const *,AutoScz *)

- ea: `0x180115b88`
- end: `0x180115e25`
- name: `?GetStorageHelper@OneCoreInfoGather@@IEAAJPEB_WPEAVAutoScz@@@Z`
- size: `669`
- prototype: `int(OneCoreInfoGather *__hidden this, const wchar_t *, struct AutoScz *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1801154a0`
- `0x180115560`
- `0x180115fe0`

## callees

- `0x1800031d0`
- `0x18000f614`
- `0x18000f874`
- `0x18003d670`
- `0x180066a38`
- `0x180115b88`
- `0x180182d50`

## import_xrefs

- `ntdll!NtClose` at `0x180115de7`
- `ntdll!NtClose` at `0x180115de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115cd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180115c04`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180115c04`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180115cc5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180115cc5`

## pseudocode

```c

```
