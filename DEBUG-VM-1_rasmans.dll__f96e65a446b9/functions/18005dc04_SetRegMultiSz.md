# SetRegMultiSz

- ea: `0x18005dc04`
- end: `0x18005dd1f`
- name: `SetRegMultiSz`
- size: `283`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005b620`

## callees

- `0x18002ee78`
- `0x18005dc04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005dcfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005dcfa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005dc4d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005dc4d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dd05`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dd05`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005dc28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005dc28`

## pseudocode

```c

```
