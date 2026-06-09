# CResultSetFactory::_GetProviderConfigs(IServiceProvider *,IResultShape *,ICondition *,_GUID const &,void * *,_tagpropertykey const &)

- ea: `0x18000d078`
- end: `0x18000d1f1`
- name: `?_GetProviderConfigs@CResultSetFactory@@AEAAJPEAUIServiceProvider@@PEAUIResultShape@@PEAUICondition@@AEBU_GUID@@PEAPEAXAEBU_tagpropertykey@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct IServiceProvider *, struct IResultShape *, struct ICondition *, const struct _GUID *, void **, const struct _tagpropertykey *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180060620`
- `0x1800a62a0`

## callees

- `0x18000d078`
- `0x18000e4d4`
- `0x180070088`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d0cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d0cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d0ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d0ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d125`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d171`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d171`

## pseudocode

```c

```
