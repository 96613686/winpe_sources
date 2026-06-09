# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x18001979c`
- end: `0x18001989d`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `257`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `6`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021eb0`
- `0x18007be94`
- `0x1800820e0`
- `0x1800a3af0`
- `0x1800e0430`
- `0x180182a04`

## callees

- `0x1800182dc`
- `0x18001979c`
- `0x1800afa70`
- `0x1800afced`
- `0x1801ac010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001987e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001987e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800197f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800197f8`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800197b8`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800197b8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800197d8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800197e9`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800197d8`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800197e9`

## string_xrefs

- `0x180019824`: `ntdll.dll`

## pseudocode

```c

```
