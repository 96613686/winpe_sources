# CSyncRootManagerCache::TryGetCustomStateHandlerForPath(ushort const *,_GUID *,Windows::Storage::Provider::IStorageProviderItemPropertySource * *)

- ea: `0x1800048e0`
- end: `0x180004999`
- name: `?TryGetCustomStateHandlerForPath@CSyncRootManagerCache@@AEAAJPEBGPEAU_GUID@@PEAPEAUIStorageProviderItemPropertySource@Provider@Storage@Windows@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(CSyncRootManagerCache *__hidden this, const unsigned __int16 *, struct _GUID *, struct Windows::Storage::Provider::IStorageProviderItemPropertySource **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800046ec`

## callees

- `0x1800048e0`
- `0x1800077c8`
- `0x18000a058`
- `0x18001267c`
- `0x180024198`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004962`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004962`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004909`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004909`

## string_xrefs

- `0x180004985`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c

```
