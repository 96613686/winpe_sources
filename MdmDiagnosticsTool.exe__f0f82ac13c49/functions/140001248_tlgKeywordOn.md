# _tlgKeywordOn

- ea: `0x140001248`
- end: `0x140001266`
- name: `_tlgKeywordOn`
- size: `30`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400091b0`
- `0x1400091f0`
- `0x14000930c`
- `0x1400093d8`

## callees

- `0x140001248`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return (*(_QWORD *)(a1 + 16) & a2) != 0 && (a2 & *(_QWORD *)(a1 + 24)) == *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x140001248  mov     r8, [rcx+18h]
0x14000124c  mov     rax, [rcx+10h]
0x140001250  test    rdx, rax
0x140001253  jz      short loc_140001263
0x140001255  mov     rax, r8
0x140001258  and     rax, rdx
0x14000125b  cmp     rax, r8
0x14000125e  jnz     short loc_140001263
0x140001260  mov     al, 1
0x140001262  retn
0x140001263  xor     al, al
0x140001265  retn
```
