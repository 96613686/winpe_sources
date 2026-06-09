# _tlgKeywordOn

- ea: `0x180011f00`
- end: `0x180011f1e`
- name: `_tlgKeywordOn`
- size: `30`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180010650`
- `0x180011a90`
- `0x180011f30`
- `0x180012170`
- `0x1800177d0`
- `0x1800178f0`
- `0x180019620`

## callees

- `0x180011f00`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return (*(_QWORD *)(a1 + 16) & a2) != 0 && (a2 & *(_QWORD *)(a1 + 24)) == *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x180011f00  mov     r8, [rcx+18h]
0x180011f04  mov     rax, [rcx+10h]
0x180011f08  test    rdx, rax
0x180011f0b  jz      short loc_180011F1B
0x180011f0d  mov     rax, r8
0x180011f10  and     rax, rdx
0x180011f13  cmp     rax, r8
0x180011f16  jnz     short loc_180011F1B
0x180011f18  mov     al, 1
0x180011f1a  retn
0x180011f1b  xor     al, al
0x180011f1d  retn
```
