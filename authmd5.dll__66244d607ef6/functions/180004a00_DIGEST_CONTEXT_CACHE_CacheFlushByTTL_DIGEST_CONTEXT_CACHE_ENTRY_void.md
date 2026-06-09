# DIGEST_CONTEXT_CACHE::CacheFlushByTTL(DIGEST_CONTEXT_CACHE_ENTRY *,void *)

- ea: `0x180004a00`
- end: `0x180004a12`
- name: `?CacheFlushByTTL@DIGEST_CONTEXT_CACHE@@CA?AW4LK_PREDICATE@@PEAVDIGEST_CONTEXT_CACHE_ENTRY@@PEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall DIGEST_CONTEXT_CACHE::CacheFlushByTTL(__int64 a1)
{
  return 3 - (unsigned int)(_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) != 1);
}

```

## disassembly

```asm
0x180004a00  or      eax, 0FFFFFFFFh
0x180004a03  lock xadd [rcx+10h], eax
0x180004a08  dec     eax
0x180004a0a  neg     eax
0x180004a0c  sbb     eax, eax
0x180004a0e  add     eax, 3
0x180004a11  retn
```
