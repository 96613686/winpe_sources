# GetSecurityInfoExW

- ea: `0x180050bd0`
- end: `0x180050ee3`
- name: `GetSecurityInfoExW`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050950`

## callees

- `0x18002d8a0`
- `0x180050bd0`
- `0x180053004`
- `0x180074010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180050ddb`
- `msvcrt!wcsncpy_s` at `0x180050e91`
- `msvcrt!wcsncpy_s` at `0x180050ddb`
- `msvcrt!wcsncpy_s` at `0x180050e91`
- `ntdll!RtlNtStatusToDosError` at `0x180050d40`
- `ntdll!RtlNtStatusToDosError` at `0x180050d40`
- `KERNELBASE!LocalAlloc` at `0x180050d9d`
- `KERNELBASE!LocalAlloc` at `0x180050e53`
- `KERNELBASE!LocalAlloc` at `0x180050d9d`
- `KERNELBASE!LocalAlloc` at `0x180050e53`
- `KERNEL32!LocalFree` at `0x180050dee`
- `KERNEL32!LocalFree` at `0x180050e04`
- `KERNEL32!LocalFree` at `0x180050ea4`
- `KERNEL32!LocalFree` at `0x180050eba`
- `KERNEL32!LocalFree` at `0x180050dee`
- `KERNEL32!LocalFree` at `0x180050e04`
- `KERNEL32!LocalFree` at `0x180050ea4`
- `KERNEL32!LocalFree` at `0x180050eba`

## pseudocode

```c

```
