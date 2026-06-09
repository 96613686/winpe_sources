# CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_Pred(void const *,void *)

- ea: `0x180004c80`
- end: `0x180004c8c`
- name: `?_Pred@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA?AW4LK_PREDICATE@@PEBXPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_Pred(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD))a2)(a1, *(_QWORD *)(a2 + 16));
}

```

## disassembly

```asm
0x180004c80  mov     rax, [rdx]
0x180004c83  mov     rdx, [rdx+10h]
0x180004c87  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
