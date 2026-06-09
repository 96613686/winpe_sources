# MsiEnumFeaturesW

- ea: `0x18004aff0`
- end: `0x18004b2d5`
- name: `MsiEnumFeaturesW`
- size: `741`
- prototype: `UINT __stdcall(LPCWSTR szProduct, DWORD iFeatureIndex, LPWSTR lpFeatureBuf, LPWSTR lpParentBuf)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18004cf08`
- `0x1801136c0`
- `0x180186c70`

## callees

- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x1800227d0`
- `0x180025560`
- `0x18004aff0`
- `0x18004b560`
- `0x180050cf0`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18004b178`
- `ADVAPI32!RegEnumValueW` at `0x18004b178`
- `ADVAPI32!RegQueryValueExW` at `0x18004b27b`
- `ADVAPI32!RegQueryValueExW` at `0x18004b27b`
- `KERNEL32!InitializeCriticalSection` at `0x18004b07a`
- `KERNEL32!InitializeCriticalSection` at `0x18004b07a`
- `KERNEL32!lstrlenW` at `0x18004b035`
- `KERNEL32!lstrlenW` at `0x18004b092`
- `KERNEL32!lstrlenW` at `0x18004b035`
- `KERNEL32!lstrlenW` at `0x18004b092`
- `KERNEL32!GlobalFree` at `0x18004b0fc`
- `KERNEL32!GlobalFree` at `0x18004b1be`
- `KERNEL32!GlobalFree` at `0x18004b2a7`
- `KERNEL32!GlobalFree` at `0x18004b2ca`
- `KERNEL32!GlobalFree` at `0x18004b0fc`
- `KERNEL32!GlobalFree` at `0x18004b1be`
- `KERNEL32!GlobalFree` at `0x18004b2a7`
- `KERNEL32!GlobalFree` at `0x18004b2ca`

## pseudocode

```c

```
