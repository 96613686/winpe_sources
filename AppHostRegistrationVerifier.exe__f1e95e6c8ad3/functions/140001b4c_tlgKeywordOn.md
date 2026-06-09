# _tlgKeywordOn

- ea: `0x140001b4c`
- end: `0x140001b72`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400096a4`
- `0x14000d610`
- `0x14000dc48`
- `0x14000dfdc`
- `0x14000e0ec`
- `0x14000e1e0`
- `0x14000e348`
- `0x14000e430`
- `0x14000e660`
- `0x14000e890`
- `0x140010c80`

## callees

- `0x140001b4c`

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
0x140001b4c  mov     rax, rcx
0x140001b4f  test    rdx, rdx
0x140001b52  jz      short loc_140001B6C
0x140001b54  mov     rcx, [rcx+18h]
0x140001b58  mov     rax, [rax+10h]
0x140001b5c  test    rdx, rax
0x140001b5f  jz      short loc_140001B6F
0x140001b61  mov     rax, rcx
0x140001b64  and     rax, rdx
0x140001b67  cmp     rax, rcx
0x140001b6a  jnz     short loc_140001B6F
0x140001b6c  mov     al, 1
0x140001b6e  retn
0x140001b6f  xor     al, al
0x140001b71  retn
```
