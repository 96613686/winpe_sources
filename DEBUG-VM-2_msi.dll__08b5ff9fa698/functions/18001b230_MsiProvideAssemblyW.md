# MsiProvideAssemblyW

- ea: `0x18001b230`
- end: `0x18001ba36`
- name: `MsiProvideAssemblyW`
- size: `2054`
- prototype: `UINT __stdcall(LPCWSTR szAssemblyName, LPCWSTR szAppContext, DWORD dwInstallMode, DWORD dwAssemblyInfo, LPWSTR lpPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180107748`
- `0x18016c520`
- `0x1801adb00`

## callees

- `0x18001b230`
- `0x18001ba40`
- `0x18001bb30`
- `0x18001cab0`
- `0x18001d960`
- `0x180025a18`
- `0x18004c654`
- `0x180066074`
- `0x180074bd0`
- `0x1800a9f70`
- `0x18025ab12`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18001b87e`
- `KERNEL32!GlobalAlloc` at `0x18001b87e`
- `KERNEL32!lstrlenW` at `0x18001b566`
- `KERNEL32!lstrlenW` at `0x18001b9aa`
- `KERNEL32!lstrlenW` at `0x18001b566`
- `KERNEL32!lstrlenW` at `0x18001b9aa`
- `KERNEL32!GlobalFree` at `0x18001b5c8`
- `KERNEL32!GlobalFree` at `0x18001b5f1`
- `KERNEL32!GlobalFree` at `0x18001b61a`
- `KERNEL32!GlobalFree` at `0x18001b6a5`
- `KERNEL32!GlobalFree` at `0x18001b6e4`
- `KERNEL32!GlobalFree` at `0x18001b70d`
- `KERNEL32!GlobalFree` at `0x18001b736`
- `KERNEL32!GlobalFree` at `0x18001b7c9`
- `KERNEL32!GlobalFree` at `0x18001b84f`
- `KERNEL32!GlobalFree` at `0x18001b8a5`
- `KERNEL32!GlobalFree` at `0x18001b5c8`
- `KERNEL32!GlobalFree` at `0x18001b5f1`
- `KERNEL32!GlobalFree` at `0x18001b61a`
- `KERNEL32!GlobalFree` at `0x18001b6a5`
- `KERNEL32!GlobalFree` at `0x18001b6e4`
- `KERNEL32!GlobalFree` at `0x18001b70d`
- `KERNEL32!GlobalFree` at `0x18001b736`
- `KERNEL32!GlobalFree` at `0x18001b7c9`
- `KERNEL32!GlobalFree` at `0x18001b84f`
- `KERNEL32!GlobalFree` at `0x18001b8a5`

## string_xrefs

- `0x18001b944`: `Pathbuf: %X, pcchPathBuf: %X`
- `0x18001b901`: `Entering MsiProvideAssembly. AssemblyName: %s, AppContext: %s, InstallMode: %d`
- `0x18001b668`: `MsiProvideAssembly is returning: %u`

## pseudocode

```c

```
