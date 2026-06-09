# GetRegistrySecureBinary

- ea: `0x140080314`
- end: `0x14008060e`
- name: `GetRegistrySecureBinary`
- size: `762`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, _QWORD *, DWORD *, int, _DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14008249c`
- `0x140083330`

## callees

- `0x140002946`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x1400698ec`
- `0x14006998c`
- `0x140074b70`
- `0x140080314`
- `0x140086e76`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400803a2`
- `KERNEL32!GetLastError` at `0x140080494`
- `KERNEL32!GetLastError` at `0x140080542`
- `KERNEL32!GetLastError` at `0x14008058d`
- `KERNEL32!GetLastError` at `0x1400803a2`
- `KERNEL32!GetLastError` at `0x140080494`
- `KERNEL32!GetLastError` at `0x140080542`
- `KERNEL32!GetLastError` at `0x14008058d`
- `KERNEL32!LocalFree` at `0x1400805d0`
- `KERNEL32!LocalFree` at `0x1400805d0`
- `CRYPT32!CryptUnprotectData` at `0x140080532`
- `CRYPT32!CryptUnprotectData` at `0x140080532`

## pseudocode

```c

```
