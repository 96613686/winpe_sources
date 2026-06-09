# _tlgKeywordOn

- ea: `0x140001b5c`
- end: `0x140001b82`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140008210`
- `0x14000a4f0`
- `0x14000e1f4`
- `0x14000e994`
- `0x14000ed0c`

## callees

- `0x140001b5c`

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
0x140001b5c  mov     rax, rcx
0x140001b5f  test    rdx, rdx
0x140001b62  jz      short loc_140001B7C
0x140001b64  mov     rcx, [rcx+18h]
0x140001b68  mov     rax, [rax+10h]
0x140001b6c  test    rdx, rax
0x140001b6f  jz      short loc_140001B7F
0x140001b71  mov     rax, rcx
0x140001b74  and     rax, rdx
0x140001b77  cmp     rax, rcx
0x140001b7a  jnz     short loc_140001B7F
0x140001b7c  mov     al, 1
0x140001b7e  retn
0x140001b7f  xor     al, al
0x140001b81  retn
```
