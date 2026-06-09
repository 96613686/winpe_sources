# _tlgKeywordOn

- ea: `0x140001104`
- end: `0x14000112a`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b454`
- `0x14000ca40`
- `0x14000cd30`
- `0x14000cf10`

## callees

- `0x140001104`

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
0x140001104  mov     rax, rcx
0x140001107  test    rdx, rdx
0x14000110a  jz      short loc_140001124
0x14000110c  mov     rcx, [rcx+18h]
0x140001110  mov     rax, [rax+10h]
0x140001114  test    rdx, rax
0x140001117  jz      short loc_140001127
0x140001119  mov     rax, rcx
0x14000111c  and     rax, rdx
0x14000111f  cmp     rax, rcx
0x140001122  jnz     short loc_140001127
0x140001124  mov     al, 1
0x140001126  retn
0x140001127  xor     al, al
0x140001129  retn
```
