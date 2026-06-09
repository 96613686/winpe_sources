# FH4::UWMap4::ReadEntry(uchar * *)

- ea: `0x14000ddf4`
- end: `0x14000de92`
- name: `?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z`
- size: `158`
- prototype: `void __fastcall(FH4::UWMap4 *__hidden this, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d960`
- `0x14000dec0`
- `0x14000df94`

## callees

- `0x14000ddf4`

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
0x14000ddf4  mov     r8, [rdx]
0x14000ddf7  lea     r11, cs:140000000h
0x14000ddfe  mov     r10, rcx
0x14000de01  mov     r9, rdx
0x14000de04  movzx   ecx, byte ptr [r8]
0x14000de08  and     ecx, 0Fh
0x14000de0b  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000de14  mov     cl, [rcx+r11+115B0h]
0x14000de1c  sub     r8, rax
0x14000de1f  mov     eax, [r8-4]
0x14000de23  shr     eax, cl
0x14000de25  mov     ecx, eax
0x14000de27  mov     [rdx], r8
0x14000de2a  and     ecx, 3
0x14000de2d  shr     eax, 2
0x14000de30  mov     [r10+14h], ecx
0x14000de34  mov     [r10+10h], eax
0x14000de38  cmp     ecx, 1
0x14000de3b  jz      short loc_14000DE58
0x14000de3d  cmp     ecx, 2
0x14000de40  jz      short loc_14000DE58
0x14000de42  cmp     ecx, 3
0x14000de45  jnz     short locret_14000DE91
0x14000de47  mov     rax, [rdx]
0x14000de4a  mov     ecx, [rax]
0x14000de4c  add     rax, 4
0x14000de50  mov     [rdx], rax
0x14000de53  mov     [r10+18h], ecx
0x14000de57  retn
0x14000de58  mov     rax, [rdx]
0x14000de5b  mov     ecx, [rax]
0x14000de5d  add     rax, 4
0x14000de61  mov     [rdx], rax
0x14000de64  mov     [r10+18h], ecx
0x14000de68  mov     rdx, [rdx]
0x14000de6b  movzx   ecx, byte ptr [rdx]
0x14000de6e  and     ecx, 0Fh
0x14000de71  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000de7a  mov     cl, [rcx+r11+115B0h]
0x14000de82  sub     rdx, rax
0x14000de85  mov     eax, [rdx-4]
0x14000de88  shr     eax, cl
0x14000de8a  mov     [r9], rdx
0x14000de8d  mov     [r10+1Ch], eax
0x14000de91  retn
```
