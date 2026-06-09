# _tlgKeywordOn

- ea: `0x18000172c`
- end: `0x180001752`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c4c`
- `0x180007d78`
- `0x180009d30`

## callees

- `0x18000172c`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool result; // al

  result = 1;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_QWORD *)(a1 + 16) & a2) == 0 || (a2 & v3) != v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000172c  mov     rax, rcx
0x18000172f  test    rdx, rdx
0x180001732  jz      short loc_18000174C
0x180001734  mov     rcx, [rcx+18h]
0x180001738  mov     rax, [rax+10h]
0x18000173c  test    rdx, rax
0x18000173f  jz      short loc_18000174F
0x180001741  mov     rax, rcx
0x180001744  and     rax, rdx
0x180001747  cmp     rax, rcx
0x18000174a  jnz     short loc_18000174F
0x18000174c  mov     al, 1
0x18000174e  retn
0x18000174f  xor     al, al
0x180001751  retn
```
