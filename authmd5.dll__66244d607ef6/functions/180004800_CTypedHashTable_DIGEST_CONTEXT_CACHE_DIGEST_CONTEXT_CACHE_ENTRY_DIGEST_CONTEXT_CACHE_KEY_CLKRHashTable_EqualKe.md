# CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x180004800`
- end: `0x180004817`
- name: `?_EqualKeys@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA_N_K0@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004800`

## pseudocode

```c
bool __fastcall CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_EqualKeys(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  v2 = *a1 - *a2;
  if ( *a1 == *a2 )
    v2 = a1[1] - a2[1];
  return v2 == 0;
}

```

## disassembly

```asm
0x180004800  mov     rax, [rcx]
0x180004803  sub     rax, [rdx]
0x180004806  jnz     short loc_180004810
0x180004808  mov     rax, [rcx+8]
0x18000480c  sub     rax, [rdx+8]
0x180004810  test    rax, rax
0x180004813  setz    al
0x180004816  retn
```
