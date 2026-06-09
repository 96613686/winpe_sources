# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x180031bac`
- end: `0x180031c4a`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180030c38`
- `0x180030cbc`
- `0x1800315f0`
- `0x180031c5c`
- `0x180031c94`
- `0x180031cd4`
- `0x180031dfc`
- `0x180031ecc`

## callees

- `0x180031bac`

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
  *((_DWORD *)this + 5) = v7;
  *((_DWORD *)this + 4) = v6 >> 2;
  if ( v7 == 1 || v7 == 2 )
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
0x180031bac  mov     r8, [rdx]
0x180031baf  lea     r11, cs:180000000h
0x180031bb6  mov     r10, rcx
0x180031bb9  mov     r9, rdx
0x180031bbc  movzx   ecx, byte ptr [r8]
0x180031bc0  and     ecx, 0Fh
0x180031bc3  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x180031bcc  mov     cl, [rcx+r11+6D0B0h]
0x180031bd4  sub     r8, rax
0x180031bd7  mov     eax, [r8-4]
0x180031bdb  shr     eax, cl
0x180031bdd  mov     ecx, eax
0x180031bdf  mov     [rdx], r8
0x180031be2  and     ecx, 3
0x180031be5  shr     eax, 2
0x180031be8  mov     [r10+14h], ecx
0x180031bec  mov     [r10+10h], eax
0x180031bf0  cmp     ecx, 1
0x180031bf3  jz      short loc_180031C10
0x180031bf5  cmp     ecx, 2
0x180031bf8  jz      short loc_180031C10
0x180031bfa  cmp     ecx, 3
0x180031bfd  jnz     short locret_180031C49
0x180031bff  mov     rax, [rdx]
0x180031c02  mov     ecx, [rax]
0x180031c04  add     rax, 4
0x180031c08  mov     [rdx], rax
0x180031c0b  mov     [r10+18h], ecx
0x180031c0f  retn
0x180031c10  mov     rax, [rdx]
0x180031c13  mov     ecx, [rax]
0x180031c15  add     rax, 4
0x180031c19  mov     [rdx], rax
0x180031c1c  mov     [r10+18h], ecx
0x180031c20  mov     rdx, [rdx]
0x180031c23  movzx   ecx, byte ptr [rdx]
0x180031c26  and     ecx, 0Fh
0x180031c29  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x180031c32  mov     cl, [rcx+r11+6D0B0h]
0x180031c3a  sub     rdx, rax
0x180031c3d  mov     eax, [rdx-4]
0x180031c40  shr     eax, cl
0x180031c42  mov     [r9], rdx
0x180031c45  mov     [r10+1Ch], eax
0x180031c49  retn
```
