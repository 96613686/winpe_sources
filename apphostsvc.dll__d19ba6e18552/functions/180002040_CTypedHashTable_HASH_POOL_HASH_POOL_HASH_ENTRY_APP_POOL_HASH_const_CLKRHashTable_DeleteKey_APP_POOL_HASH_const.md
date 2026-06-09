# CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::DeleteKey(APP_POOL_HASH const * const)

- ea: `0x180002040`
- end: `0x180002047`
- name: `?DeleteKey@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@QEAA?AW4LK_RETCODE@@QEBUAPP_POOL_HASH@@@Z`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180002040`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::DeleteKey(
        __int64 a1,
        __int64 a2)
{
  return CLKRHashTable::DeleteKey(a1, a2);
}

```

## disassembly

```asm
0x180002040  jmp     cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; public: enum LK_RETCODE CTypedHashTable<class HASH_POOL_HASH, class POOL_HASH_ENTRY, struct APP_POOL_HASH const *, class CLKRHashTable>::DeleteKey(struct APP_POOL_HASH const * const)
```
