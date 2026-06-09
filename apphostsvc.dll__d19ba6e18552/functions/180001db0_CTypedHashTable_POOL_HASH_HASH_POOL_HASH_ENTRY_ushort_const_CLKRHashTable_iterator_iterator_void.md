# CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,ushort const *,CLKRHashTable>::iterator::~iterator(void)

- ea: `0x180001db0`
- end: `0x180001db7`
- name: `??1iterator@?$CTypedHashTable@VPOOL_HASH_HASH@@VPOOL_HASH_ENTRY@@PEBGVCLKRHashTable@@@@QEAA@XZ`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000928a`
- `0x18000929c`
- `0x1800092d4`
- `0x1800092e6`

## import_xrefs

- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180001db0`

## pseudocode

```c
// attributes: thunk
void __fastcall CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,unsigned short const *,CLKRHashTable>::iterator::~iterator(
        CLKRHashTable_Iterator *a1)
{
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator(a1);
}

```

## disassembly

```asm
0x180001db0  jmp     cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
```
