# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x180066144`
- end: `0x18006621c`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800407a4`
- `0x180066224`

## callees

- `0x180002a06`
- `0x180002aaf`
- `0x180066144`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800661fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800661fb`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006617a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180066185`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006617a`
- `ntdll!RtlReleaseSRWLockShared` at `0x180066185`
- `ntdll!RtlAcquireSRWLockShared` at `0x180066160`
- `ntdll!RtlAcquireSRWLockShared` at `0x180066160`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180066204`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180066204`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006618e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006618e`

## string_xrefs

- `0x18006619f`: `ntdll.dll`

## pseudocode

```c

```
