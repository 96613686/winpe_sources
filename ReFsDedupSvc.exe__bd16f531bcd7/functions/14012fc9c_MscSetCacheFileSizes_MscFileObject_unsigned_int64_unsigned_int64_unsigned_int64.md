# MscSetCacheFileSizes(MscFileObject *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x14012fc9c`
- end: `0x14012fd75`
- name: `?MscSetCacheFileSizes@@YAJPEAUMscFileObject@@PEA_K11@Z`
- size: `217`
- prototype: `__int64 __fastcall(struct MscFileObject *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1401363f0`

## callees

- `0x140004be0`
- `0x140004f44`
- `0x1400057e0`
- `0x14012fc9c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x14012fcd4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14012fcd4`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012fd4f`
- `ntdll!RtlReleaseSRWLockShared` at `0x14012fd4f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012fd5d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14012fd5d`

## pseudocode

```c

```
