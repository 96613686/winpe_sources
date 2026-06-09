# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x18001393c`
- end: `0x180013ac4`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001205c`
- `0x180012804`
- `0x1800132c0`

## callees

- `0x18001393c`

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
0x18001393c  xor     eax, eax
0x18001393e  lea     r11, __ImageBase
0x180013945  mov     [rcx+18h], al
0x180013948  xorps   xmm0, xmm0
0x18001394b  mov     [rcx+1Ch], rax
0x18001394f  mov     r8, rcx
0x180013952  mov     [rcx+24h], rax
0x180013956  movups  xmmword ptr [rcx+30h], xmm0
0x18001395a  mov     rax, [rcx+8]
0x18001395e  mov     r10b, [rax]
0x180013961  lea     rdx, [rax+1]
0x180013965  mov     [rcx+18h], r10b
0x180013969  mov     [rcx+8], rdx
0x18001396d  test    r10b, 1
0x180013971  jz      short loc_18001399A
0x180013973  movzx   ecx, byte ptr [rdx]
0x180013976  and     ecx, 0Fh
0x180013979  movsx   rax, byte ptr [rcx+r11+177D8h]
0x180013982  mov     cl, [rcx+r11+177E8h]
0x18001398a  sub     rdx, rax
0x18001398d  mov     eax, [rdx-4]
0x180013990  shr     eax, cl
0x180013992  mov     [r8+1Ch], eax
0x180013996  mov     [r8+8], rdx
0x18001399a  test    r10b, 2
0x18001399e  jz      short loc_1800139AE
0x1800139a0  mov     eax, [rdx]
0x1800139a2  add     rdx, 4
0x1800139a6  mov     [r8+8], rdx
0x1800139aa  mov     [r8+20h], eax
0x1800139ae  test    r10b, 4
0x1800139b2  jz      short loc_1800139DB
0x1800139b4  movzx   ecx, byte ptr [rdx]
0x1800139b7  and     ecx, 0Fh
0x1800139ba  movsx   rax, byte ptr [rcx+r11+177D8h]
0x1800139c3  mov     cl, [rcx+r11+177E8h]
0x1800139cb  sub     rdx, rax
0x1800139ce  mov     eax, [rdx-4]
0x1800139d1  shr     eax, cl
0x1800139d3  mov     [r8+24h], eax
0x1800139d7  mov     [r8+8], rdx
0x1800139db  mov     eax, [rdx]
0x1800139dd  lea     r9, [rdx+4]
0x1800139e1  mov     [r8+28h], eax
0x1800139e5  mov     al, r10b
0x1800139e8  and     al, 30h
0x1800139ea  mov     [r8+8], r9
0x1800139ee  test    r10b, 8
0x1800139f2  jz      short loc_180013A2F
0x1800139f4  cmp     al, 10h
0x1800139f6  jnz     short loc_180013A08
0x1800139f8  movsxd  rcx, dword ptr [r9]
0x1800139fb  lea     rax, [r9+4]
0x1800139ff  mov     [r8+8], rax
0x180013a03  mov     [r8+30h], rcx
0x180013a07  retn
0x180013a08  cmp     al, 20h ; ' '
0x180013a0a  jnz     locret_180013AC3
0x180013a10  movsxd  rax, dword ptr [r9]
0x180013a13  lea     rdx, [r9+4]
0x180013a17  mov     [r8+8], rdx
0x180013a1b  mov     [r8+30h], rax
0x180013a1f  lea     rax, [rdx+4]
0x180013a23  movsxd  rcx, dword ptr [rdx]
0x180013a26  mov     [r8+8], rax
0x180013a2a  jmp     loc_180013ABF
0x180013a2f  cmp     al, 10h
0x180013a31  jnz     short loc_180013A63
0x180013a33  movzx   ecx, byte ptr [r9]
0x180013a37  and     ecx, 0Fh
0x180013a3a  movsx   rax, byte ptr [rcx+r11+177D8h]
0x180013a43  mov     cl, [rcx+r11+177E8h]
0x180013a4b  sub     r9, rax
0x180013a4e  mov     eax, [r8+48h]
0x180013a52  mov     edx, [r9-4]
0x180013a56  shr     edx, cl
0x180013a58  add     eax, edx
0x180013a5a  mov     [r8+8], r9
0x180013a5e  mov     [r8+30h], rax
0x180013a62  retn
0x180013a63  cmp     al, 20h ; ' '
0x180013a65  jnz     short locret_180013AC3
0x180013a67  movzx   ecx, byte ptr [r9]
0x180013a6b  mov     edx, [r8+48h]
0x180013a6f  and     ecx, 0Fh
0x180013a72  movsx   rax, byte ptr [rcx+r11+177D8h]
0x180013a7b  mov     cl, [rcx+r11+177E8h]
0x180013a83  sub     r9, rax
0x180013a86  mov     eax, [r9-4]
0x180013a8a  shr     eax, cl
0x180013a8c  mov     [r8+8], r9
0x180013a90  lea     ecx, [rdx+rax]
0x180013a93  mov     [r8+30h], rcx
0x180013a97  movzx   ecx, byte ptr [r9]
0x180013a9b  and     ecx, 0Fh
0x180013a9e  movsx   rax, byte ptr [rcx+r11+177D8h]
0x180013aa7  mov     cl, [rcx+r11+177E8h]
0x180013aaf  sub     r9, rax
0x180013ab2  mov     eax, [r9-4]
0x180013ab6  shr     eax, cl
0x180013ab8  mov     [r8+8], r9
0x180013abc  lea     ecx, [rdx+rax]
0x180013abf  mov     [r8+38h], rcx
0x180013ac3  retn
```
