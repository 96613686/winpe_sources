# _tlgKeywordOn

- ea: `0x140001f1c`
- end: `0x140001f42`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140016010`
- `0x1400163f8`
- `0x140016644`
- `0x140017808`
- `0x140017880`
- `0x1400178e8`
- `0x140017978`
- `0x1400179f0`
- `0x140017a80`
- `0x140017b10`
- `0x140017ba0`
- `0x140017c2c`
- `0x140017cbc`
- `0x140017d4c`
- `0x140017dec`
- `0x140017e7c`

## callees

- `0x140001f1c`

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
0x140001f1c  mov     rax, rcx
0x140001f1f  test    rdx, rdx
0x140001f22  jz      short loc_140001F3C
0x140001f24  mov     rcx, [rcx+18h]
0x140001f28  mov     rax, [rax+10h]
0x140001f2c  test    rdx, rax
0x140001f2f  jz      short loc_140001F3F
0x140001f31  mov     rax, rcx
0x140001f34  and     rax, rdx
0x140001f37  cmp     rax, rcx
0x140001f3a  jnz     short loc_140001F3F
0x140001f3c  mov     al, 1
0x140001f3e  retn
0x140001f3f  xor     al, al
0x140001f41  retn
```
