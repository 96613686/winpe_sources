# DIGEST_CONTEXT_CACHE::ScavengerCallback(void *,uchar)

- ea: `0x180004c00`
- end: `0x180004c3c`
- name: `?ScavengerCallback@DIGEST_CONTEXT_CACHE@@CAXPEAXE@Z`
- size: `60`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180004c31`
- `iisutil!?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z` at `0x180004c31`

## pseudocode

```c
void __fastcall DIGEST_CONTEXT_CACHE::ScavengerCallback(char *a1)
{
  _QWORD v1[5]; // [rsp+20h] [rbp-28h] BYREF

  v1[1] = 0;
  v1[0] = &DIGEST_CONTEXT_CACHE::CacheFlushByTTL;
  v1[2] = 0;
  CLKRHashTable::DeleteIf(
    (CLKRHashTable *)(a1 + 8),
    (enum LK_PREDICATE (__high *)(const void *, void *))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_Pred,
    v1);
}

```

## disassembly

```asm
0x180004c00  mov     r11, rsp
0x180004c03  sub     rsp, 48h
0x180004c07  lea     rax, ?CacheFlushByTTL@DIGEST_CONTEXT_CACHE@@CA?AW4LK_PREDICATE@@PEAVDIGEST_CONTEXT_CACHE_ENTRY@@PEAX@Z; DIGEST_CONTEXT_CACHE::CacheFlushByTTL(DIGEST_CONTEXT_CACHE_ENTRY *,void *)
0x180004c0e  mov     qword ptr [r11-20h], 0
0x180004c16  add     rcx, 8
0x180004c1a  mov     [r11-28h], rax
0x180004c1e  lea     r8, [r11-28h]
0x180004c22  mov     qword ptr [r11-18h], 0
0x180004c2a  lea     rdx, ?_Pred@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_Pred(void const *,void *)
0x180004c31  call    cs:__imp_?DeleteIf@CLKRHashTable@@QEAAKP6A?AW4LK_PREDICATE@@PEBXPEAX@Z1@Z; CLKRHashTable::DeleteIf(LK_PREDICATE (*)(void const *,void *),void *)
0x180004c37  add     rsp, 48h
0x180004c3b  retn
```
