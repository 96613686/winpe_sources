# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x18001426c`
- end: `0x18001430a`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180013d30`
- `0x180014338`
- `0x18001440c`

## callees

- `0x18001426c`

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
0x18001426c  mov     r8, [rdx]
0x18001426f  lea     r11, __ImageBase
0x180014276  mov     r10, rcx
0x180014279  mov     r9, rdx
0x18001427c  movzx   ecx, byte ptr [r8]
0x180014280  and     ecx, 0Fh
0x180014283  movsx   rax, byte ptr [rcx+r11+177D8h]
0x18001428c  mov     cl, [rcx+r11+177E8h]
0x180014294  sub     r8, rax
0x180014297  mov     eax, [r8-4]
0x18001429b  shr     eax, cl
0x18001429d  mov     ecx, eax
0x18001429f  mov     [rdx], r8
0x1800142a2  and     ecx, 3
0x1800142a5  shr     eax, 2
0x1800142a8  mov     [r10+14h], ecx
0x1800142ac  mov     [r10+10h], eax
0x1800142b0  cmp     ecx, 1
0x1800142b3  jz      short loc_1800142D0
0x1800142b5  cmp     ecx, 2
0x1800142b8  jz      short loc_1800142D0
0x1800142ba  cmp     ecx, 3
0x1800142bd  jnz     short locret_180014309
0x1800142bf  mov     rax, [rdx]
0x1800142c2  mov     ecx, [rax]
0x1800142c4  add     rax, 4
0x1800142c8  mov     [rdx], rax
0x1800142cb  mov     [r10+18h], ecx
0x1800142cf  retn
0x1800142d0  mov     rax, [rdx]
0x1800142d3  mov     ecx, [rax]
0x1800142d5  add     rax, 4
0x1800142d9  mov     [rdx], rax
0x1800142dc  mov     [r10+18h], ecx
0x1800142e0  mov     rdx, [rdx]
0x1800142e3  movzx   ecx, byte ptr [rdx]
0x1800142e6  and     ecx, 0Fh
0x1800142e9  movsx   rax, byte ptr [rcx+r11+177D8h]
0x1800142f2  mov     cl, [rcx+r11+177E8h]
0x1800142fa  sub     rdx, rax
0x1800142fd  mov     eax, [rdx-4]
0x180014300  shr     eax, cl
0x180014302  mov     [r9], rdx
0x180014305  mov     [r10+1Ch], eax
0x180014309  retn
```
