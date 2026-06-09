# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x14000a794`
- end: `0x14000a91c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008f40`
- `0x1400096f0`
- `0x14000a190`

## callees

- `0x14000a794`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)&FH4::s_negLengthTab + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x14000a794  xor     eax, eax
0x14000a796  lea     r11, cs:140000000h
0x14000a79d  mov     [rcx+18h], al
0x14000a7a0  xorps   xmm0, xmm0
0x14000a7a3  mov     [rcx+1Ch], rax
0x14000a7a7  mov     r8, rcx
0x14000a7aa  mov     [rcx+24h], rax
0x14000a7ae  movups  xmmword ptr [rcx+30h], xmm0
0x14000a7b2  mov     rax, [rcx+8]
0x14000a7b6  mov     r10b, [rax]
0x14000a7b9  lea     rdx, [rax+1]
0x14000a7bd  mov     [rcx+18h], r10b
0x14000a7c1  mov     [rcx+8], rdx
0x14000a7c5  test    r10b, 1
0x14000a7c9  jz      short loc_14000A7F2
0x14000a7cb  movzx   ecx, byte ptr [rdx]
0x14000a7ce  and     ecx, 0Fh
0x14000a7d1  movsx   rax, byte ptr [rcx+r11+280B0h]
0x14000a7da  mov     cl, [rcx+r11+280C0h]
0x14000a7e2  sub     rdx, rax
0x14000a7e5  mov     eax, [rdx-4]
0x14000a7e8  shr     eax, cl
0x14000a7ea  mov     [r8+1Ch], eax
0x14000a7ee  mov     [r8+8], rdx
0x14000a7f2  test    r10b, 2
0x14000a7f6  jz      short loc_14000A806
0x14000a7f8  mov     eax, [rdx]
0x14000a7fa  add     rdx, 4
0x14000a7fe  mov     [r8+8], rdx
0x14000a802  mov     [r8+20h], eax
0x14000a806  test    r10b, 4
0x14000a80a  jz      short loc_14000A833
0x14000a80c  movzx   ecx, byte ptr [rdx]
0x14000a80f  and     ecx, 0Fh
0x14000a812  movsx   rax, byte ptr [rcx+r11+280B0h]
0x14000a81b  mov     cl, [rcx+r11+280C0h]
0x14000a823  sub     rdx, rax
0x14000a826  mov     eax, [rdx-4]
0x14000a829  shr     eax, cl
0x14000a82b  mov     [r8+24h], eax
0x14000a82f  mov     [r8+8], rdx
0x14000a833  mov     eax, [rdx]
0x14000a835  lea     r9, [rdx+4]
0x14000a839  mov     [r8+28h], eax
0x14000a83d  mov     al, r10b
0x14000a840  and     al, 30h
0x14000a842  mov     [r8+8], r9
0x14000a846  test    r10b, 8
0x14000a84a  jz      short loc_14000A887
0x14000a84c  cmp     al, 10h
0x14000a84e  jnz     short loc_14000A860
0x14000a850  movsxd  rcx, dword ptr [r9]
0x14000a853  lea     rax, [r9+4]
0x14000a857  mov     [r8+8], rax
0x14000a85b  mov     [r8+30h], rcx
0x14000a85f  retn
0x14000a860  cmp     al, 20h ; ' '
0x14000a862  jnz     locret_14000A91B
0x14000a868  movsxd  rax, dword ptr [r9]
0x14000a86b  lea     rdx, [r9+4]
0x14000a86f  mov     [r8+8], rdx
0x14000a873  mov     [r8+30h], rax
0x14000a877  lea     rax, [rdx+4]
0x14000a87b  movsxd  rcx, dword ptr [rdx]
0x14000a87e  mov     [r8+8], rax
0x14000a882  jmp     loc_14000A917
0x14000a887  cmp     al, 10h
0x14000a889  jnz     short loc_14000A8BB
0x14000a88b  movzx   ecx, byte ptr [r9]
0x14000a88f  and     ecx, 0Fh
0x14000a892  movsx   rax, byte ptr [rcx+r11+280B0h]
0x14000a89b  mov     cl, [rcx+r11+280C0h]
0x14000a8a3  sub     r9, rax
0x14000a8a6  mov     eax, [r8+48h]
0x14000a8aa  mov     edx, [r9-4]
0x14000a8ae  shr     edx, cl
0x14000a8b0  add     eax, edx
0x14000a8b2  mov     [r8+8], r9
0x14000a8b6  mov     [r8+30h], rax
0x14000a8ba  retn
0x14000a8bb  cmp     al, 20h ; ' '
0x14000a8bd  jnz     short locret_14000A91B
0x14000a8bf  movzx   ecx, byte ptr [r9]
0x14000a8c3  mov     edx, [r8+48h]
0x14000a8c7  and     ecx, 0Fh
0x14000a8ca  movsx   rax, byte ptr [rcx+r11+280B0h]
0x14000a8d3  mov     cl, [rcx+r11+280C0h]
0x14000a8db  sub     r9, rax
0x14000a8de  mov     eax, [r9-4]
0x14000a8e2  shr     eax, cl
0x14000a8e4  mov     [r8+8], r9
0x14000a8e8  lea     ecx, [rdx+rax]
0x14000a8eb  mov     [r8+30h], rcx
0x14000a8ef  movzx   ecx, byte ptr [r9]
0x14000a8f3  and     ecx, 0Fh
0x14000a8f6  movsx   rax, byte ptr [rcx+r11+280B0h]
0x14000a8ff  mov     cl, [rcx+r11+280C0h]
0x14000a907  sub     r9, rax
0x14000a90a  mov     eax, [r9-4]
0x14000a90e  shr     eax, cl
0x14000a910  mov     [r8+8], r9
0x14000a914  lea     ecx, [rdx+rax]
0x14000a917  mov     [r8+38h], rcx
0x14000a91b  retn
```
