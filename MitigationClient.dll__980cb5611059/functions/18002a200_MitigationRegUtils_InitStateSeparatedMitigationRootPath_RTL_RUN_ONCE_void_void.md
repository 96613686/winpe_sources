# MitigationRegUtils::InitStateSeparatedMitigationRootPath(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18002a200`
- end: `0x18002a2d2`
- name: `?InitStateSeparatedMitigationRootPath@MitigationRegUtils@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x180013ebc`
- `0x180017c84`
- `0x180018858`
- `0x18002a200`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002a261`
- `ntdll!RtlNtStatusToDosError` at `0x18002a261`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002a259`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002a259`

## pseudocode

```c

```
