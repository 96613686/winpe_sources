# CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)

- ea: `0x180004820`
- end: `0x180004825`
- name: `?_ExtractKey@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_ExtractKey(
        __int64 a1)
{
  return a1 + 24;
}

```

## disassembly

```asm
0x180004820  lea     rax, [rcx+18h]
0x180004824  retn
```
