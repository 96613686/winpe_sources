# ProvideComponent(ushort const *,ushort const *,ushort const *,ulong,ushort *,ulong *,bool,CRFSCachedSourceInfo &)

- ea: `0x18004b75c`
- end: `0x18004c5b7`
- name: `?ProvideComponent@@YAIPEBG00KPEAGPEAK_NAEAVCRFSCachedSourceInfo@@@Z`
- size: `3675`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, DWORD dwReinstallMode, unsigned __int16 *, unsigned int *, bool, struct CRFSCachedSourceInfo *)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004c654`
- `0x180199bf0`

## callees

- `0x180013264`
- `0x180014848`
- `0x180015690`
- `0x180015950`
- `0x18001cab0`
- `0x18001d960`
- `0x1800250d4`
- `0x180025a18`
- `0x18004b560`
- `0x18004b75c`
- `0x18004c5c0`
- `0x180050cf0`
- `0x18006fcf4`
- `0x180073d9c`
- `0x1800f2c00`
- `0x18014c880`
- `0x18014df38`
- `0x180154618`
- `0x180195270`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18004b90c`
- `KERNEL32!InitializeCriticalSection` at `0x18004b90c`
- `KERNEL32!lstrlenW` at `0x18004bc66`
- `KERNEL32!lstrlenW` at `0x18004bc66`
- `KERNEL32!GlobalFree` at `0x18004b847`
- `KERNEL32!GlobalFree` at `0x18004b863`
- `KERNEL32!GlobalFree` at `0x18004b983`
- `KERNEL32!GlobalFree` at `0x18004b9a1`
- `KERNEL32!GlobalFree` at `0x18004baa4`
- `KERNEL32!GlobalFree` at `0x18004babe`
- `KERNEL32!GlobalFree` at `0x18004bd0f`
- `KERNEL32!GlobalFree` at `0x18004bd3d`
- `KERNEL32!GlobalFree` at `0x18004be00`
- `KERNEL32!GlobalFree` at `0x18004be52`
- `KERNEL32!GlobalFree` at `0x18004be6c`
- `KERNEL32!GlobalFree` at `0x18004bf97`
- `KERNEL32!GlobalFree` at `0x18004c035`
- `KERNEL32!GlobalFree` at `0x18004c063`
- `KERNEL32!GlobalFree` at `0x18004c103`
- `KERNEL32!GlobalFree` at `0x18004c11d`
- `KERNEL32!GlobalFree` at `0x18004c14f`
- `KERNEL32!GlobalFree` at `0x18004c1a1`
- `KERNEL32!GlobalFree` at `0x18004c1bb`
- `KERNEL32!GlobalFree` at `0x18004c1db`
- `KERNEL32!GlobalFree` at `0x18004c239`
- `KERNEL32!GlobalFree` at `0x18004c253`
- `KERNEL32!GlobalFree` at `0x18004c284`
- `KERNEL32!GlobalFree` at `0x18004c2d6`
- `KERNEL32!GlobalFree` at `0x18004c2f0`
- `KERNEL32!GlobalFree` at `0x18004c310`
- `KERNEL32!GlobalFree` at `0x18004c343`
- `KERNEL32!GlobalFree` at `0x18004c395`
- `KERNEL32!GlobalFree` at `0x18004c3af`
- `KERNEL32!GlobalFree` at `0x18004c3f3`
- `KERNEL32!GlobalFree` at `0x18004c40d`
- `KERNEL32!GlobalFree` at `0x18004c453`
- `KERNEL32!GlobalFree` at `0x18004c46d`
- `KERNEL32!GlobalFree` at `0x18004c4d5`
- `KERNEL32!GlobalFree` at `0x18004c4ef`
- `KERNEL32!GlobalFree` at `0x18004c52c`
- `KERNEL32!GlobalFree` at `0x18004c546`
- `KERNEL32!GlobalFree` at `0x18004c58f`
- `KERNEL32!GlobalFree` at `0x18004c5a9`
- `KERNEL32!GlobalFree` at `0x18004b847`
- `KERNEL32!GlobalFree` at `0x18004b863`
- `KERNEL32!GlobalFree` at `0x18004b983`
- `KERNEL32!GlobalFree` at `0x18004b9a1`
- `KERNEL32!GlobalFree` at `0x18004baa4`
- `KERNEL32!GlobalFree` at `0x18004babe`
- `KERNEL32!GlobalFree` at `0x18004bd0f`
- `KERNEL32!GlobalFree` at `0x18004bd3d`
- `KERNEL32!GlobalFree` at `0x18004be00`
- `KERNEL32!GlobalFree` at `0x18004be52`
- `KERNEL32!GlobalFree` at `0x18004be6c`
- `KERNEL32!GlobalFree` at `0x18004bf97`
- `KERNEL32!GlobalFree` at `0x18004c035`
- `KERNEL32!GlobalFree` at `0x18004c063`
- `KERNEL32!GlobalFree` at `0x18004c103`
- `KERNEL32!GlobalFree` at `0x18004c11d`
- `KERNEL32!GlobalFree` at `0x18004c14f`
- `KERNEL32!GlobalFree` at `0x18004c1a1`
- `KERNEL32!GlobalFree` at `0x18004c1bb`
- `KERNEL32!GlobalFree` at `0x18004c1db`
- `KERNEL32!GlobalFree` at `0x18004c239`
- `KERNEL32!GlobalFree` at `0x18004c253`
- `KERNEL32!GlobalFree` at `0x18004c284`
- `KERNEL32!GlobalFree` at `0x18004c2d6`
- `KERNEL32!GlobalFree` at `0x18004c2f0`
- `KERNEL32!GlobalFree` at `0x18004c310`
- `KERNEL32!GlobalFree` at `0x18004c343`
- `KERNEL32!GlobalFree` at `0x18004c395`
- `KERNEL32!GlobalFree` at `0x18004c3af`
- `KERNEL32!GlobalFree` at `0x18004c3f3`
- `KERNEL32!GlobalFree` at `0x18004c40d`
- `KERNEL32!GlobalFree` at `0x18004c453`
- `KERNEL32!GlobalFree` at `0x18004c46d`
- `KERNEL32!GlobalFree` at `0x18004c4d5`
- `KERNEL32!GlobalFree` at `0x18004c4ef`
- `KERNEL32!GlobalFree` at `0x18004c52c`
- `KERNEL32!GlobalFree` at `0x18004c546`
- `KERNEL32!GlobalFree` at `0x18004c58f`
- `KERNEL32!GlobalFree` at `0x18004c5a9`

## pseudocode

```c

```
