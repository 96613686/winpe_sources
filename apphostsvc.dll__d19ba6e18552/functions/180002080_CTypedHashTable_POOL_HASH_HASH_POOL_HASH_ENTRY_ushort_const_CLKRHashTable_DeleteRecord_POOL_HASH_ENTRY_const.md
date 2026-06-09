# CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,ushort const *,CLKRHashTable>::DeleteRecord(POOL_HASH_ENTRY const *)

- ea: `0x180002080`
- end: `0x180002087`
- name: `?DeleteRecord@?$CTypedHashTable@VPOOL_HASH_HASH@@VPOOL_HASH_ENTRY@@PEBGVCLKRHashTable@@@@QEAA?AW4LK_RETCODE@@PEBVPOOL_HASH_ENTRY@@@Z`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180002080`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,unsigned short const *,CLKRHashTable>::DeleteRecord(
        __int64 a1,
        __int64 a2)
{
  return CLKRHashTable::DeleteRecord(a1, a2);
}

```

## disassembly

```asm
0x180002080  jmp     cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; public: enum LK_RETCODE CTypedHashTable<class HASH_POOL_HASH, class POOL_HASH_ENTRY, struct APP_POOL_HASH const *, class CLKRHashTable>::DeleteRecord(class POOL_HASH_ENTRY const *)
```
