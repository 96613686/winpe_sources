# _tlgKeywordOn

- ea: `0x140001258`
- end: `0x140001277`
- name: `_tlgKeywordOn`
- size: `31`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400097d4`
- `0x140009814`
- `0x140009938`
- `0x140009a08`

## callees

- `0x140001258`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return (*(_QWORD *)(a1 + 16) & a2) != 0 && (a2 & *(_QWORD *)(a1 + 24)) == *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x140001258  mov     r8, [rcx+18h]
0x14000125c  mov     rax, [rcx+10h]
0x140001260  test    rdx, rax
0x140001263  jz      short loc_140001274
0x140001265  mov     rax, r8
0x140001268  and     rax, rdx
0x14000126b  cmp     rax, r8
0x14000126e  jnz     short loc_140001274
0x140001270  mov     al, 1
0x140001272  retn
0x140001274  xor     al, al
0x140001276  retn
```
