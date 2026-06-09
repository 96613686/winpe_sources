# CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x1800047e0`
- end: `0x1800047f8`
- name: `?_CalcKeyHash@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800047e0`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(
        unsigned __int8 *a1)
{
  __int64 result; // rax
  __int64 v2; // r8
  int v3; // edx

  LODWORD(result) = 0;
  v2 = 16;
  do
  {
    v3 = *a1++;
    result = (unsigned int)(v3 + 101 * result);
    --v2;
  }
  while ( v2 );
  return result;
}

```

## disassembly

```asm
0x1800047e0  xor     eax, eax
0x1800047e2  lea     r8d, [rax+10h]
0x1800047e6  movzx   edx, byte ptr [rcx]
0x1800047e9  inc     rcx
0x1800047ec  imul    eax, 65h ; 'e'
0x1800047ef  add     eax, edx
0x1800047f1  sub     r8, 1
0x1800047f5  jnz     short loc_1800047E6
0x1800047f7  retn
```
