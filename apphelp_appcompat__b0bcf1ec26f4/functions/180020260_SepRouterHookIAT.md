# SepRouterHookIAT

- ea: `0x180020260`
- end: `0x18002061e`
- name: `SepRouterHookIAT`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001fca0`

## callees

- `0x18000f114`
- `0x180020260`
- `0x180020624`
- `0x1800209f8`
- `0x180020a68`

## import_xrefs

- `ntdll!LdrFindEntryForAddress` at `0x180020337`
- `ntdll!LdrFindEntryForAddress` at `0x180020337`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020390`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180020390`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002041c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800204f8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002041c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800204f8`
- `ntdll!_wcsicmp` at `0x180020302`
- `ntdll!_wcsicmp` at `0x180020302`

## string_xrefs

- `0x180020475`: `Excluding already hooked module %S`

## pseudocode

```c

```
