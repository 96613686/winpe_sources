# CConfigManager::GetInt(IRequestContext *,ConfigSetting,ulong *,WSManConfigSource *)

- ea: `0x180046e50`
- end: `0x180047983`
- name: `?GetInt@CConfigManager@@QEAAHPEAVIRequestContext@@W4ConfigSetting@@PEAKPEAW4WSManConfigSource@@@Z`
- size: `2867`
- prototype: `int __high(struct IRequestContext *, enum ConfigSetting, unsigned int *, enum WSManConfigSource *)`
- caller_count: `9`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180024128`
- `0x18003f3f8`
- `0x180046870`
- `0x18004697c`
- `0x180046d70`
- `0x18005eba0`
- `0x180107ce0`
- `0x18018ffe8`
- `0x1801a6784`

## callees

- `0x180005d10`
- `0x180010030`
- `0x18002c920`
- `0x180046200`
- `0x180046e50`
- `0x180047990`
- `0x1800621e0`
- `0x1800e2f68`
- `0x1801004a0`
- `0x180103850`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x180125ec4`
- `0x180193bb8`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18004742a`
- `msvcrt!_wtoi` at `0x18004785b`
- `msvcrt!_wtoi` at `0x18004742a`
- `msvcrt!_wtoi` at `0x18004785b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800475ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047638`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800475ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475fa`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18004745a`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18004745a`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18004751a`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18004751a`
- `miutils!RtlReleaseFastLockExclusive` at `0x180047507`
- `miutils!RtlReleaseFastLockExclusive` at `0x180047507`

## string_xrefs

- `0x18004794d`: `onecore\admin\wmi\wmx\config\configregistry.cpp`
- `0x1800476a0`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180047972`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x180047704`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`

## pseudocode

```c

```
