# GetObjectGenericMapping

- ea: `0x1800755d0`
- end: `0x180075800`
- name: `GetObjectGenericMapping`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180075808`

## callees

- `0x18002bfe0`
- `0x1800755d0`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800756ea`
- `KERNEL32!GetLastError` at `0x1800756ea`
- `KERNEL32!LocalFree` at `0x1800757b4`
- `KERNEL32!LocalFree` at `0x1800757b4`
- `KERNEL32!LocalAlloc` at `0x1800756d6`
- `KERNEL32!LocalAlloc` at `0x1800756d6`
- `ntdll!NtQueryObject` at `0x180075675`
- `ntdll!NtQueryObject` at `0x18007572a`
- `ntdll!NtQueryObject` at `0x180075675`
- `ntdll!NtQueryObject` at `0x18007572a`

## string_xrefs

- `0x18007560d`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x18007574d`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x1800757df`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`

## pseudocode

```c

```
