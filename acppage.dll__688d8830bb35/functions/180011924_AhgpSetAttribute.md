# AhgpSetAttribute

- ea: `0x180011924`
- end: `0x180011998`
- name: `AhgpSetAttribute`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010d10`
- `0x18001101c`
- `0x18001123c`

## callees

- `0x180011924`

## pseudocode

```c
__int64 __fastcall AhgpSetAttribute(__int64 a1, unsigned __int16 a2, _DWORD *a3)
{
  int v3; // r9d
  unsigned int v4; // r10d

  v3 = *(_DWORD *)(a1 + 4);
  v4 = 1;
  if ( (v3 & 1) == 0 )
  {
    if ( a3 )
    {
      switch ( dword_18001B594[2 * a2] )
      {
        case 16384:
          *(_DWORD *)(a1 + 8) = *a3;
          break;
        case 20480:
          *(_QWORD *)(a1 + 8) = *(_QWORD *)a3;
          break;
        case 24576:
          *(_QWORD *)(a1 + 8) = a3;
          break;
        default:
          return 0;
      }
      *(_WORD *)a1 = a2;
      *(_DWORD *)(a1 + 4) = v3 | 1;
      return v4;
    }
    *(_DWORD *)(a1 + 4) = v3 & 0xFFFFFFFC | 2;
  }
  return v4;
}

```

## disassembly

```asm
0x180011924  mov     r9d, [rcx+4]
0x180011928  mov     r10d, 1
0x18001192e  mov     r11, rcx
0x180011931  test    r10b, r9b
0x180011934  jnz     short loc_180011994
0x180011936  test    r8, r8
0x180011939  jnz     short loc_180011949
0x18001193b  and     r9d, 0FFFFFFFEh
0x18001193f  or      r9d, 2
0x180011943  mov     [rcx+4], r9d
0x180011947  jmp     short loc_180011994
0x180011949  movzx   eax, dx
0x18001194c  lea     rcx, dword_18001B594
0x180011953  cmp     dword ptr [rcx+rax*8], 4000h
0x18001195a  jz      short loc_180011982
0x18001195c  cmp     dword ptr [rcx+rax*8], 5000h
0x180011963  jz      short loc_180011979
0x180011965  cmp     dword ptr [rcx+rax*8], 6000h
0x18001196c  jz      short loc_180011973
0x18001196e  xor     r10d, r10d
0x180011971  jmp     short loc_180011994
0x180011973  mov     [r11+8], r8
0x180011977  jmp     short loc_180011989
0x180011979  mov     rax, [r8]
0x18001197c  mov     [r11+8], rax
0x180011980  jmp     short loc_180011989
0x180011982  mov     ecx, [r8]
0x180011985  mov     [r11+8], ecx
0x180011989  or      r9d, r10d
0x18001198c  mov     [r11], dx
0x180011990  mov     [r11+4], r9d
0x180011994  mov     eax, r10d
0x180011997  retn
```
