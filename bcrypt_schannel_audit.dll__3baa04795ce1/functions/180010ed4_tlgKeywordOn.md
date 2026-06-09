# _tlgKeywordOn

- ea: `0x180010ed4`
- end: `0x180010ef3`
- name: `_tlgKeywordOn`
- size: `31`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070d0`
- `0x1800101c0`
- `0x18001181c`
- `0x180014510`
- `0x180014740`
- `0x180019500`
- `0x180019920`

## callees

- `0x180010ed4`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return (*(_QWORD *)(a1 + 16) & a2) != 0 && (a2 & *(_QWORD *)(a1 + 24)) == *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x180010ed4  mov     r8, [rcx+18h]
0x180010ed8  mov     rax, [rcx+10h]
0x180010edc  test    rdx, rax
0x180010edf  jz      short loc_180010EF0
0x180010ee1  mov     rax, r8
0x180010ee4  and     rax, rdx
0x180010ee7  cmp     rax, r8
0x180010eea  jnz     short loc_180010EF0
0x180010eec  mov     al, 1
0x180010eee  retn
0x180010ef0  xor     al, al
0x180010ef2  retn
```
