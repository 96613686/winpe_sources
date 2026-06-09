# CSyncRootManagerCache::GetHandlerHelper(CSyncRootManagerCache::HandlerType,ushort const *,_GUID const &,void * *)

- ea: `0x1800641e4`
- end: `0x180064309`
- name: `?GetHandlerHelper@CSyncRootManagerCache@@AEAAJW4HandlerType@1@PEBGAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `int __high(enum HandlerType, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180065260`
- `0x180065740`
- `0x1800657d0`

## callees

- `0x180004a54`
- `0x1800092d0`
- `0x18000964c`
- `0x18001be38`
- `0x1800641e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180064288`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180064288`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180064231`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180064231`

## pseudocode

```c

```
