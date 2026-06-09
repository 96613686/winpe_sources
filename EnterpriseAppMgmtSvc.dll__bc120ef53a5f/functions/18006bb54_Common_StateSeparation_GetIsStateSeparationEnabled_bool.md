# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x18006bb54`
- end: `0x18006bc51`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `253`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800443b0`
- `0x18006bc58`

## callees

- `0x180002a56`
- `0x180002aff`
- `0x18006bb54`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006bc23`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006bc23`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bb90`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bba1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bb90`
- `ntdll!RtlReleaseSRWLockShared` at `0x18006bba1`
- `ntdll!RtlAcquireSRWLockShared` at `0x18006bb70`
- `ntdll!RtlAcquireSRWLockShared` at `0x18006bb70`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006bc32`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006bc32`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006bbb0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006bbb0`

## string_xrefs

- `0x18006bbc7`: `ntdll.dll`

## pseudocode

```c

```
