# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x18000b338`
- end: `0x18000b3d4`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `156`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aeb8`
- `0x18000b3f0`
- `0x18000b4c0`

## callees

- `0x18000b338`

## pseudocode

```c
void __fastcall FH4::UWMap4::ReadEntry(FH4::UWMap4 *this, unsigned __int8 **a2)
{
  __int64 v4; // rcx
  unsigned __int8 *v5; // r8
  unsigned int v6; // eax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int *v10; // rdx
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax

  v4 = **a2 & 0xF;
  v5 = &(*a2)[-*((char *)&FH4::s_negLengthTab + v4)];
  v6 = *((_DWORD *)v5 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v4);
  *a2 = v5;
  v7 = v6 & 3;
  *((_DWORD *)this + 4) = v6 >> 2;
  *((_DWORD *)this + 5) = v7;
  if ( (unsigned int)(v7 - 1) <= 1 )
  {
    v9 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v9;
    v10 = (int *)*a2;
    v11 = *(_BYTE *)v10 & 0xF;
    v12 = (unsigned __int8 *)v10 - *((char *)&FH4::s_negLengthTab + v11);
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
    *a2 = v12;
    *((_DWORD *)this + 7) = v13;
  }
  else if ( v7 == 3 )
  {
    v8 = *(_DWORD *)*a2;
    *a2 += 4;
    *((_DWORD *)this + 6) = v8;
  }
}

```

## disassembly

```asm
0x18000b338  mov     r8, [rdx]
0x18000b33b  lea     r11, cs:180000000h
0x18000b342  mov     r10, rcx
0x18000b345  mov     r9, rdx
0x18000b348  movzx   ecx, byte ptr [r8]
0x18000b34c  and     ecx, 0Fh
0x18000b34f  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000b358  mov     cl, [rcx+r11+26800h]
0x18000b360  sub     r8, rax
0x18000b363  mov     eax, [r8-4]
0x18000b367  shr     eax, cl
0x18000b369  mov     ecx, eax
0x18000b36b  mov     [rdx], r8
0x18000b36e  and     ecx, 3
0x18000b371  shr     eax, 2
0x18000b374  mov     [r10+10h], eax
0x18000b378  mov     [r10+14h], ecx
0x18000b37c  lea     eax, [rcx-1]
0x18000b37f  cmp     eax, 1
0x18000b382  jbe     short loc_18000B39A
0x18000b384  cmp     ecx, 3
0x18000b387  jnz     short locret_18000B3D3
0x18000b389  mov     rax, [rdx]
0x18000b38c  mov     ecx, [rax]
0x18000b38e  add     rax, 4
0x18000b392  mov     [rdx], rax
0x18000b395  mov     [r10+18h], ecx
0x18000b399  retn
0x18000b39a  mov     rax, [rdx]
0x18000b39d  mov     ecx, [rax]
0x18000b39f  add     rax, 4
0x18000b3a3  mov     [rdx], rax
0x18000b3a6  mov     [r10+18h], ecx
0x18000b3aa  mov     rdx, [rdx]
0x18000b3ad  movzx   ecx, byte ptr [rdx]
0x18000b3b0  and     ecx, 0Fh
0x18000b3b3  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000b3bc  mov     cl, [rcx+r11+26800h]
0x18000b3c4  sub     rdx, rax
0x18000b3c7  mov     eax, [rdx-4]
0x18000b3ca  shr     eax, cl
0x18000b3cc  mov     [r9], rdx
0x18000b3cf  mov     [r10+1Ch], eax
0x18000b3d3  retn
```
