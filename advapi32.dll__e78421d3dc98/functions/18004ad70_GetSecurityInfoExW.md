# GetSecurityInfoExW

- ea: `0x18004ad70`
- end: `0x18004b048`
- name: `GetSecurityInfoExW`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ab40`

## callees

- `0x18002a088`
- `0x18004ad70`
- `0x18004d000`
- `0x180066010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18004af6f`
- `msvcrt!wcsncpy_s` at `0x18004b009`
- `msvcrt!wcsncpy_s` at `0x18004af6f`
- `msvcrt!wcsncpy_s` at `0x18004b009`
- `ntdll!RtlNtStatusToDosError` at `0x18004aee0`
- `ntdll!RtlNtStatusToDosError` at `0x18004aee0`
- `KERNELBASE!LocalAlloc` at `0x18004af37`
- `KERNELBASE!LocalAlloc` at `0x18004afd1`
- `KERNELBASE!LocalAlloc` at `0x18004af37`
- `KERNELBASE!LocalAlloc` at `0x18004afd1`
- `KERNEL32!LocalFree` at `0x18004af7c`
- `KERNEL32!LocalFree` at `0x18004af8c`
- `KERNEL32!LocalFree` at `0x18004b016`
- `KERNEL32!LocalFree` at `0x18004b026`
- `KERNEL32!LocalFree` at `0x18004af7c`
- `KERNEL32!LocalFree` at `0x18004af8c`
- `KERNEL32!LocalFree` at `0x18004b016`
- `KERNEL32!LocalFree` at `0x18004b026`

## pseudocode

```c

```
