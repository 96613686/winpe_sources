# _tlgKeywordOn

- ea: `0x140001f30`
- end: `0x140001f57`
- name: `_tlgKeywordOn`
- size: `39`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140016cb0`
- `0x140017098`
- `0x1400172ec`
- `0x1400184e8`
- `0x140018560`
- `0x1400185c8`
- `0x14001865c`
- `0x1400186d4`
- `0x140018768`
- `0x1400187fc`
- `0x140018890`
- `0x140018920`
- `0x1400189b4`
- `0x140018a48`
- `0x140018aec`
- `0x140018b80`

## callees

- `0x140001f30`

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
0x140001f30  mov     rax, rcx
0x140001f33  test    rdx, rdx
0x140001f36  jz      short loc_140001F50
0x140001f38  mov     rcx, [rcx+18h]
0x140001f3c  mov     rax, [rax+10h]
0x140001f40  test    rdx, rax
0x140001f43  jz      short loc_140001F54
0x140001f45  mov     rax, rcx
0x140001f48  and     rax, rdx
0x140001f4b  cmp     rax, rcx
0x140001f4e  jnz     short loc_140001F54
0x140001f50  mov     al, 1
0x140001f52  retn
0x140001f54  xor     al, al
0x140001f56  retn
```
