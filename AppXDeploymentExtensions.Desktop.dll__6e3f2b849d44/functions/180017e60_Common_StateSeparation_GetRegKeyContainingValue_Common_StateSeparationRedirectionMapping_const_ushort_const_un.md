# Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)

- ea: `0x180017e60`
- end: `0x1800182d3`
- name: `?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(const struct Common::StateSeparationRedirectionMapping *, const unsigned __int16 **, HKEY, const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018ffc`
- `0x180022410`
- `0x18007ac34`
- `0x18007de68`
- `0x1801288a0`

## callees

- `0x18000a138`
- `0x180012fc8`
- `0x180017ba0`
- `0x180017e60`
- `0x1800182dc`
- `0x18001adb4`
- `0x18001f678`
- `0x180021e80`
- `0x18007bd4c`
- `0x1800af1bc`
- `0x1800afa70`
- `0x1800afaa0`
- `0x1800afaac`
- `0x1800afced`
- `0x180172d8c`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018095`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800180f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018095`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800180f8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017f0d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017f0d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180017eb9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180017eb9`
- `ntdll!RtlAcquireSRWLockShared` at `0x180017e8b`
- `ntdll!RtlAcquireSRWLockShared` at `0x180017e8b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180017eaa`
- `ntdll!RtlReleaseSRWLockShared` at `0x180018084`
- `ntdll!RtlReleaseSRWLockShared` at `0x180017eaa`
- `ntdll!RtlReleaseSRWLockShared` at `0x180018084`

## string_xrefs

- `0x1800182a1`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180017ede`: `ntdll.dll`
- `0x180018130`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180018161`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800181f7`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180018242`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c

```
