# std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)

- ea: `0x180009b54`
- end: `0x180009b88`
- name: `?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z`
- size: `52`
- prototype: `unsigned __int64 __fastcall(unsigned __int64, const unsigned __int8 *const, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000939c`
- `0x18000cb08`
- `0x18000de20`
- `0x18000de70`

## callees

- `0x180009b54`

## pseudocode

```c
__int64 __fastcall std::_Fnv1a_append_bytes(__int64 a1, const unsigned __int8 *const a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r9
  __int64 i; // rcx
  __int64 v5; // rax

  v3 = 0;
  for ( i = 0xCBF29CE484222325uLL; v3 < a3; i = 0x100000001B3LL * (v5 ^ i) )
    v5 = a2[v3++];
  return i;
}

```

## disassembly

```asm
0x180009b54  xor     r9d, r9d
0x180009b57  mov     rcx, 0CBF29CE484222325h
0x180009b61  test    r8, r8
0x180009b64  jz      short loc_180009B84
0x180009b66  movzx   eax, byte ptr [rdx+r9]
0x180009b6b  mov     r10, 100000001B3h
0x180009b75  xor     rcx, rax
0x180009b78  inc     r9
0x180009b7b  imul    rcx, r10
0x180009b7f  cmp     r9, r8
0x180009b82  jb      short loc_180009B66
0x180009b84  mov     rax, rcx
0x180009b87  retn
```
