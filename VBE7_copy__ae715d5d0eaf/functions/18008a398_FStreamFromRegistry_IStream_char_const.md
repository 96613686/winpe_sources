# FStreamFromRegistry(IStream * *,char const *)

- ea: `0x18008a398`
- end: `0x18008a4cc`
- name: `?FStreamFromRegistry@@YAHPEAPEAUIStream@@PEBD@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct IStream **, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800863b0`
- `0x1800d0eb0`

## callees

- `0x1800610c0`
- `0x18008a398`
- `0x180379380`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18008a40b`
- `KERNEL32!GlobalAlloc` at `0x18008a40b`
- `KERNEL32!GlobalLock` at `0x18008a420`
- `KERNEL32!GlobalLock` at `0x18008a420`
- `KERNEL32!GlobalUnlock` at `0x18008a457`
- `KERNEL32!GlobalUnlock` at `0x18008a497`
- `KERNEL32!GlobalUnlock` at `0x18008a457`
- `KERNEL32!GlobalUnlock` at `0x18008a497`
- `KERNEL32!GlobalFree` at `0x18008a4a4`
- `KERNEL32!GlobalFree` at `0x18008a4a4`
- `ADVAPI32!RegQueryValueExA` at `0x18008a3f7`
- `ADVAPI32!RegQueryValueExA` at `0x18008a44a`
- `ADVAPI32!RegQueryValueExA` at `0x18008a3f7`
- `ADVAPI32!RegQueryValueExA` at `0x18008a44a`
- `ADVAPI32!RegCloseKey` at `0x18008a4b3`
- `ADVAPI32!RegCloseKey` at `0x18008a4b3`
- `ole32!CreateStreamOnHGlobal` at `0x18008a46c`
- `ole32!CreateStreamOnHGlobal` at `0x18008a46c`

## pseudocode

```c

```
