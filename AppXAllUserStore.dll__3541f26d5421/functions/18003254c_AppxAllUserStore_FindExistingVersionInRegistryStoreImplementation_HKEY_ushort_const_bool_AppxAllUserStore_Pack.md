# AppxAllUserStore::FindExistingVersionInRegistryStoreImplementation(HKEY__ *,ushort const *,bool,AppxAllUserStore::PackageVersionFound *,AppxAllUserStore::_PackageInfo * *)

- ea: `0x18003254c`
- end: `0x180032e53`
- name: `?FindExistingVersionInRegistryStoreImplementation@AppxAllUserStore@@YAJPEAUHKEY__@@PEBG_NPEAW4PackageVersionFound@1@PEAPEAU_PackageInfo@1@@Z`
- size: `2311`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY this@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, enum AppxAllUserStore::PackageVersionFound *, struct AppxAllUserStore::_PackageInfo **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18002e0a0`

## callees

- `0x1800027a8`
- `0x180004920`
- `0x180004968`
- `0x180005ec8`
- `0x180006870`
- `0x180006d40`
- `0x180007a10`
- `0x180007ebc`
- `0x180008db0`
- `0x18000ce40`
- `0x18000d6a0`
- `0x18000d710`
- `0x18000d770`
- `0x180018248`
- `0x180021ea8`
- `0x18003254c`
- `0x1800467a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003270f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800328fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003270f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800328fa`

## pseudocode

```c

```
