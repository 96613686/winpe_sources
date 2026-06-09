# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x18000ae40`
- end: `0x18000aede`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a9c4`
- `0x18000aefc`
- `0x18000afcc`

## callees

- `0x18000ae40`

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
0x18000ae40  mov     r8, [rdx]
0x18000ae43  lea     r11, cs:180000000h
0x18000ae4a  mov     r10, rcx
0x18000ae4d  mov     r9, rdx
0x18000ae50  movzx   ecx, byte ptr [r8]
0x18000ae54  and     ecx, 0Fh
0x18000ae57  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000ae60  mov     cl, [rcx+r11+0D5F8h]
0x18000ae68  sub     r8, rax
0x18000ae6b  mov     eax, [r8-4]
0x18000ae6f  shr     eax, cl
0x18000ae71  mov     ecx, eax
0x18000ae73  mov     [rdx], r8
0x18000ae76  and     ecx, 3
0x18000ae79  shr     eax, 2
0x18000ae7c  mov     [r10+14h], ecx
0x18000ae80  mov     [r10+10h], eax
0x18000ae84  cmp     ecx, 1
0x18000ae87  jz      short loc_18000AEA4
0x18000ae89  cmp     ecx, 2
0x18000ae8c  jz      short loc_18000AEA4
0x18000ae8e  cmp     ecx, 3
0x18000ae91  jnz     short locret_18000AEDD
0x18000ae93  mov     rax, [rdx]
0x18000ae96  mov     ecx, [rax]
0x18000ae98  add     rax, 4
0x18000ae9c  mov     [rdx], rax
0x18000ae9f  mov     [r10+18h], ecx
0x18000aea3  retn
0x18000aea4  mov     rax, [rdx]
0x18000aea7  mov     ecx, [rax]
0x18000aea9  add     rax, 4
0x18000aead  mov     [rdx], rax
0x18000aeb0  mov     [r10+18h], ecx
0x18000aeb4  mov     rdx, [rdx]
0x18000aeb7  movzx   ecx, byte ptr [rdx]
0x18000aeba  and     ecx, 0Fh
0x18000aebd  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000aec6  mov     cl, [rcx+r11+0D5F8h]
0x18000aece  sub     rdx, rax
0x18000aed1  mov     eax, [rdx-4]
0x18000aed4  shr     eax, cl
0x18000aed6  mov     [r9], rdx
0x18000aed9  mov     [r10+1Ch], eax
0x18000aedd  retn
```
