# CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,ushort const *,CLKRHashTable>::DeleteIf(LK_PREDICATE (*)(POOL_HASH_ENTRY *,void *),void *)

- ea: `0x180002000`
- end: `0x180002037`
- name: `?DeleteIf@?$CTypedHashTable@VPOOL_HASH_HASH@@VPOOL_HASH_ENTRY@@PEBGVCLKRHashTable@@@@QEAAKP6A?AW4LK_PREDICATE@@PEAVPOOL_HASH_ENTRY@@PEAX@Z1@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002000`

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000202c`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x18000202c`

## pseudocode

```c
unsigned int __fastcall CTypedHashTable<POOL_HASH_HASH,POOL_HASH_ENTRY,unsigned short const *,CLKRHashTable>::DeleteIf(
        CLKRHashTable *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD v4[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2 )
    return 0;
  v4[0] = a2;
  v4[2] = a3;
  v4[1] = 0;
  return CLKRHashTable::DeleteIf(
           a1,
           (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Pred,
           v4);
}

```

## disassembly

```asm
0x180002000  sub     rsp, 48h; public: unsigned long CTypedHashTable<class HASH_POOL_HASH, class POOL_HASH_ENTRY, struct APP_POOL_HASH const *, class CLKRHashTable>::DeleteIf(enum LK_PREDICATE (*)(class POOL_HASH_ENTRY *, void *), void *)
0x180002004  test    rdx, rdx
0x180002007  jnz     short loc_18000200D
0x180002009  xor     eax, eax
0x18000200b  jmp     short loc_180002032
0x18000200d  mov     [rsp+48h+var_28], rdx
0x180002012  lea     rdx, ?_Pred@?$CTypedHashTable@VHASH_POOL_HASH@@VPOOL_HASH_ENTRY@@PEBUAPP_POOL_HASH@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<HASH_POOL_HASH,POOL_HASH_ENTRY,APP_POOL_HASH const *,CLKRHashTable>::_Pred(void const *,void *)
0x180002019  mov     [rsp+48h+var_18], r8
0x18000201e  lea     r8, [rsp+48h+var_28]
0x180002023  mov     [rsp+48h+var_20], 0
0x18000202c  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180002032  add     rsp, 48h
0x180002036  retn
```
