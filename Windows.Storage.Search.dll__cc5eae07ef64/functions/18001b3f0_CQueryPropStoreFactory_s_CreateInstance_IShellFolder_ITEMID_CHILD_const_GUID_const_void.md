# CQueryPropStoreFactory::s_CreateInstance(IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x18001b3f0`
- end: `0x18001b53b`
- name: `?s_CreateInstance@CQueryPropStoreFactory@@SAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(IUnknown *punk, LPCITEMIDLIST pidl, IID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18008ae74`

## callees

- `0x18001b3f0`
- `0x18001b544`
- `0x18002e0ec`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18001b46e`
- `SHCORE!IUnknown_Set` at `0x18001b46e`
- `Windows.Storage!ILFree` at `0x18001b505`
- `Windows.Storage!ILFree` at `0x18001b505`
- `Windows.Storage!ILCloneFirst` at `0x18001b451`
- `Windows.Storage!ILCloneFirst` at `0x18001b451`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001b4a7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18001b4a7`

## pseudocode

```c

```
