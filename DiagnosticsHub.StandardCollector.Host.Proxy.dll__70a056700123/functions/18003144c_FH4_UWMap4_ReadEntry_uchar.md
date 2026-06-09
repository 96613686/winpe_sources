# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x18003144c`
- end: `0x1800314ea`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800304d8`
- `0x18003055c`
- `0x180030e90`
- `0x1800314fc`
- `0x180031534`
- `0x180031574`
- `0x18003169c`
- `0x18003176c`

## callees

- `0x18003144c`

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
0x18003144c  mov     r8, [rdx]
0x18003144f  lea     r11, cs:180000000h
0x180031456  mov     r10, rcx
0x180031459  mov     r9, rdx
0x18003145c  movzx   ecx, byte ptr [r8]
0x180031460  and     ecx, 0Fh
0x180031463  movsx   rax, byte ptr [rcx+r11+699C0h]
0x18003146c  mov     cl, [rcx+r11+699D0h]
0x180031474  sub     r8, rax
0x180031477  mov     eax, [r8-4]
0x18003147b  shr     eax, cl
0x18003147d  mov     ecx, eax
0x18003147f  mov     [rdx], r8
0x180031482  and     ecx, 3
0x180031485  shr     eax, 2
0x180031488  mov     [r10+14h], ecx
0x18003148c  mov     [r10+10h], eax
0x180031490  cmp     ecx, 1
0x180031493  jz      short loc_1800314B0
0x180031495  cmp     ecx, 2
0x180031498  jz      short loc_1800314B0
0x18003149a  cmp     ecx, 3
0x18003149d  jnz     short locret_1800314E9
0x18003149f  mov     rax, [rdx]
0x1800314a2  mov     ecx, [rax]
0x1800314a4  add     rax, 4
0x1800314a8  mov     [rdx], rax
0x1800314ab  mov     [r10+18h], ecx
0x1800314af  retn
0x1800314b0  mov     rax, [rdx]
0x1800314b3  mov     ecx, [rax]
0x1800314b5  add     rax, 4
0x1800314b9  mov     [rdx], rax
0x1800314bc  mov     [r10+18h], ecx
0x1800314c0  mov     rdx, [rdx]
0x1800314c3  movzx   ecx, byte ptr [rdx]
0x1800314c6  and     ecx, 0Fh
0x1800314c9  movsx   rax, byte ptr [rcx+r11+699C0h]
0x1800314d2  mov     cl, [rcx+r11+699D0h]
0x1800314da  sub     rdx, rax
0x1800314dd  mov     eax, [rdx-4]
0x1800314e0  shr     eax, cl
0x1800314e2  mov     [r9], rdx
0x1800314e5  mov     [r10+1Ch], eax
0x1800314e9  retn
```
