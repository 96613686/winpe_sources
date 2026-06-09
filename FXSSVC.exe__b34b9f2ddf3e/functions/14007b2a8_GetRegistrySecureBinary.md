# GetRegistrySecureBinary

- ea: `0x14007b2a8`
- end: `0x14007b57d`
- name: `GetRegistrySecureBinary`
- size: `725`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14007d2d0`
- `0x14007e100`

## callees

- `0x140002926`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140065d14`
- `0x140065dbc`
- `0x140070554`
- `0x14007b2a8`
- `0x140081866`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14007b336`
- `KERNEL32!GetLastError` at `0x14007b422`
- `KERNEL32!GetLastError` at `0x14007b4c4`
- `KERNEL32!GetLastError` at `0x14007b509`
- `KERNEL32!GetLastError` at `0x14007b336`
- `KERNEL32!GetLastError` at `0x14007b422`
- `KERNEL32!GetLastError` at `0x14007b4c4`
- `KERNEL32!GetLastError` at `0x14007b509`
- `KERNEL32!LocalFree` at `0x14007b546`
- `KERNEL32!LocalFree` at `0x14007b546`
- `CRYPT32!CryptUnprotectData` at `0x14007b4ba`
- `CRYPT32!CryptUnprotectData` at `0x14007b4ba`

## pseudocode

```c

```
