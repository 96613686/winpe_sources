# AccProvpGetStringFromRegistry

- ea: `0x18002a2f4`
- end: `0x18002a419`
- name: `AccProvpGetStringFromRegistry`
- size: `293`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, HLOCAL *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180029b98`
- `0x18002a088`
- `0x18002a420`

## callees

- `0x18002a2f4`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18002a344`
- `KERNELBASE!LocalAlloc` at `0x18002a3cd`
- `KERNELBASE!LocalAlloc` at `0x18002a344`
- `KERNELBASE!LocalAlloc` at `0x18002a3cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a32f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a376`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a32f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a376`
- `KERNEL32!LocalFree` at `0x18002a385`
- `KERNEL32!LocalFree` at `0x18002a3f1`
- `KERNEL32!LocalFree` at `0x18002a407`
- `KERNEL32!LocalFree` at `0x18002a385`
- `KERNEL32!LocalFree` at `0x18002a3f1`
- `KERNEL32!LocalFree` at `0x18002a407`
- `KERNEL32!GetLastError` at `0x18002a394`
- `KERNEL32!GetLastError` at `0x18002a3fc`
- `KERNEL32!GetLastError` at `0x18002a394`
- `KERNEL32!GetLastError` at `0x18002a3fc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002a3ba`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002a3e4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002a3ba`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002a3e4`

## pseudocode

```c

```
