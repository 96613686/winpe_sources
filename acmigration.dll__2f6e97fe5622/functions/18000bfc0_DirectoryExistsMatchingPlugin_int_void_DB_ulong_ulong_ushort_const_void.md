# DirectoryExistsMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18000bfc0`
- end: `0x18000c048`
- name: `?DirectoryExistsMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `136`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, LPCWSTR lpSrc, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001cf0`
- `0x18000bfc0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000c010`
- `KERNEL32!GetFileAttributesW` at `0x18000c010`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000bffc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000bffc`

## pseudocode

```c

```
