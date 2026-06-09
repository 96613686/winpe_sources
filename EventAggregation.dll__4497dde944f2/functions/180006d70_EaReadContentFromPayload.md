# EaReadContentFromPayload

- ea: `0x180006d70`
- end: `0x180006dc1`
- name: `EaReadContentFromPayload`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006d70`

## pseudocode

```c
__int64 __fastcall EaReadContentFromPayload(__int64 a1, int a2, char a3, __int64 a4)
{
  __int64 result; // rax

  result = 0;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  if ( (a3 & 2) != 0 )
  {
    a2 -= 16;
    *(_QWORD *)a4 = a1;
    a1 += 16;
  }
  if ( (a3 & 1) != 0 )
  {
    a2 -= 16;
    *(_QWORD *)(a4 + 8) = a1;
    a1 += 16;
  }
  if ( (a3 & 4) != 0 )
  {
    a2 -= 8;
    *(_QWORD *)(a4 + 16) = a1;
    a1 += 8;
  }
  if ( a2 )
  {
    *(_QWORD *)(a4 + 24) = a1;
    *(_DWORD *)(a4 + 32) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180006d70  xorps   xmm0, xmm0
0x180006d73  xor     eax, eax
0x180006d75  movups  xmmword ptr [r9], xmm0
0x180006d79  movups  xmmword ptr [r9+10h], xmm0
0x180006d7e  mov     [r9+20h], rax
0x180006d82  test    r8b, 2
0x180006d86  jz      short loc_180006D92
0x180006d88  add     edx, 0FFFFFFF0h
0x180006d8b  mov     [r9], rcx
0x180006d8e  add     rcx, 10h
0x180006d92  test    r8b, 1
0x180006d96  jz      short loc_180006DA3
0x180006d98  add     edx, 0FFFFFFF0h
0x180006d9b  mov     [r9+8], rcx
0x180006d9f  add     rcx, 10h
0x180006da3  test    r8b, 4
0x180006da7  jz      short loc_180006DB4
0x180006da9  add     edx, 0FFFFFFF8h
0x180006dac  mov     [r9+10h], rcx
0x180006db0  add     rcx, 8
0x180006db4  test    edx, edx
0x180006db6  jz      short locret_180006DC0
0x180006db8  mov     [r9+18h], rcx
0x180006dbc  mov     [r9+20h], edx
0x180006dc0  retn
```
