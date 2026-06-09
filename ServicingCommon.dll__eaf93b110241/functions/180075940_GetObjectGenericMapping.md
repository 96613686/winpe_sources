# GetObjectGenericMapping

- ea: `0x180075940`
- end: `0x180075b70`
- name: `GetObjectGenericMapping`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180075b78`

## callees

- `0x1800280d0`
- `0x180075940`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180075a5a`
- `KERNEL32!GetLastError` at `0x180075a5a`
- `KERNEL32!LocalFree` at `0x180075b24`
- `KERNEL32!LocalFree` at `0x180075b24`
- `KERNEL32!LocalAlloc` at `0x180075a46`
- `KERNEL32!LocalAlloc` at `0x180075a46`
- `ntdll!NtQueryObject` at `0x1800759e5`
- `ntdll!NtQueryObject` at `0x180075a9a`
- `ntdll!NtQueryObject` at `0x1800759e5`
- `ntdll!NtQueryObject` at `0x180075a9a`

## string_xrefs

- `0x18007597d`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180075abd`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180075b4f`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`

## pseudocode

```c

```
