# AccProvpGetStringFromRegistry

- ea: `0x18002db08`
- end: `0x18002dc73`
- name: `AccProvpGetStringFromRegistry`
- size: `363`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, HLOCAL *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002d2fc`
- `0x18002d8a0`
- `0x18002dcc8`

## callees

- `0x18002db08`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18002db5e`
- `KERNELBASE!LocalAlloc` at `0x18002dc06`
- `KERNELBASE!LocalAlloc` at `0x18002db5e`
- `KERNELBASE!LocalAlloc` at `0x18002dc06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db96`
- `KERNEL32!LocalFree` at `0x18002dbab`
- `KERNEL32!LocalFree` at `0x18002dc36`
- `KERNEL32!LocalFree` at `0x18002dc58`
- `KERNEL32!LocalFree` at `0x18002dbab`
- `KERNEL32!LocalFree` at `0x18002dc36`
- `KERNEL32!LocalFree` at `0x18002dc58`
- `KERNEL32!GetLastError` at `0x18002dbc0`
- `KERNEL32!GetLastError` at `0x18002dc47`
- `KERNEL32!GetLastError` at `0x18002dbc0`
- `KERNEL32!GetLastError` at `0x18002dc47`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002dbed`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002dc23`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002dbed`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002dc23`

## pseudocode

```c

```
