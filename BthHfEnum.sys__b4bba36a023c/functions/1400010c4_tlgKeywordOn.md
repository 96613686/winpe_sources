# _tlgKeywordOn

- ea: `0x1400010c4`
- end: `0x1400010eb`
- name: `_tlgKeywordOn`
- size: `39`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cb40`
- `0x14000cbd0`
- `0x14000cc60`
- `0x14000cd68`
- `0x14001a288`
- `0x140028f40`
- `0x14003003c`

## callees

- `0x1400010c4`

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
0x1400010c4  mov     rax, rcx
0x1400010c7  test    rdx, rdx
0x1400010ca  jz      short loc_1400010E4
0x1400010cc  mov     rcx, [rcx+18h]
0x1400010d0  mov     rax, [rax+10h]
0x1400010d4  test    rdx, rax
0x1400010d7  jz      short loc_1400010E8
0x1400010d9  mov     rax, rcx
0x1400010dc  and     rax, rdx
0x1400010df  cmp     rax, rcx
0x1400010e2  jnz     short loc_1400010E8
0x1400010e4  mov     al, 1
0x1400010e6  retn
0x1400010e8  xor     al, al
0x1400010ea  retn
```
