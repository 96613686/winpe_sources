# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x14000d6fc`
- end: `0x14000d884`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c4a4`
- `0x14000c9e4`
- `0x14000d260`

## callees

- `0x14000d6fc`

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
0x14000d6fc  xor     eax, eax
0x14000d6fe  lea     r11, cs:140000000h
0x14000d705  mov     [rcx+18h], al
0x14000d708  xorps   xmm0, xmm0
0x14000d70b  mov     [rcx+1Ch], rax
0x14000d70f  mov     r8, rcx
0x14000d712  mov     [rcx+24h], rax
0x14000d716  movups  xmmword ptr [rcx+30h], xmm0
0x14000d71a  mov     rax, [rcx+8]
0x14000d71e  mov     r10b, [rax]
0x14000d721  lea     rdx, [rax+1]
0x14000d725  mov     [rcx+18h], r10b
0x14000d729  mov     [rcx+8], rdx
0x14000d72d  test    r10b, 1
0x14000d731  jz      short loc_14000D75A
0x14000d733  movzx   ecx, byte ptr [rdx]
0x14000d736  and     ecx, 0Fh
0x14000d739  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000d742  mov     cl, [rcx+r11+115B0h]
0x14000d74a  sub     rdx, rax
0x14000d74d  mov     eax, [rdx-4]
0x14000d750  shr     eax, cl
0x14000d752  mov     [r8+1Ch], eax
0x14000d756  mov     [r8+8], rdx
0x14000d75a  test    r10b, 2
0x14000d75e  jz      short loc_14000D76E
0x14000d760  mov     eax, [rdx]
0x14000d762  add     rdx, 4
0x14000d766  mov     [r8+8], rdx
0x14000d76a  mov     [r8+20h], eax
0x14000d76e  test    r10b, 4
0x14000d772  jz      short loc_14000D79B
0x14000d774  movzx   ecx, byte ptr [rdx]
0x14000d777  and     ecx, 0Fh
0x14000d77a  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000d783  mov     cl, [rcx+r11+115B0h]
0x14000d78b  sub     rdx, rax
0x14000d78e  mov     eax, [rdx-4]
0x14000d791  shr     eax, cl
0x14000d793  mov     [r8+24h], eax
0x14000d797  mov     [r8+8], rdx
0x14000d79b  mov     eax, [rdx]
0x14000d79d  lea     r9, [rdx+4]
0x14000d7a1  mov     [r8+28h], eax
0x14000d7a5  mov     al, r10b
0x14000d7a8  and     al, 30h
0x14000d7aa  mov     [r8+8], r9
0x14000d7ae  test    r10b, 8
0x14000d7b2  jz      short loc_14000D7EF
0x14000d7b4  cmp     al, 10h
0x14000d7b6  jnz     short loc_14000D7C8
0x14000d7b8  movsxd  rcx, dword ptr [r9]
0x14000d7bb  lea     rax, [r9+4]
0x14000d7bf  mov     [r8+8], rax
0x14000d7c3  mov     [r8+30h], rcx
0x14000d7c7  retn
0x14000d7c8  cmp     al, 20h ; ' '
0x14000d7ca  jnz     locret_14000D883
0x14000d7d0  movsxd  rax, dword ptr [r9]
0x14000d7d3  lea     rdx, [r9+4]
0x14000d7d7  mov     [r8+8], rdx
0x14000d7db  mov     [r8+30h], rax
0x14000d7df  lea     rax, [rdx+4]
0x14000d7e3  movsxd  rcx, dword ptr [rdx]
0x14000d7e6  mov     [r8+8], rax
0x14000d7ea  jmp     loc_14000D87F
0x14000d7ef  cmp     al, 10h
0x14000d7f1  jnz     short loc_14000D823
0x14000d7f3  movzx   ecx, byte ptr [r9]
0x14000d7f7  and     ecx, 0Fh
0x14000d7fa  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000d803  mov     cl, [rcx+r11+115B0h]
0x14000d80b  sub     r9, rax
0x14000d80e  mov     eax, [r8+48h]
0x14000d812  mov     edx, [r9-4]
0x14000d816  shr     edx, cl
0x14000d818  add     eax, edx
0x14000d81a  mov     [r8+8], r9
0x14000d81e  mov     [r8+30h], rax
0x14000d822  retn
0x14000d823  cmp     al, 20h ; ' '
0x14000d825  jnz     short locret_14000D883
0x14000d827  movzx   ecx, byte ptr [r9]
0x14000d82b  mov     edx, [r8+48h]
0x14000d82f  and     ecx, 0Fh
0x14000d832  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000d83b  mov     cl, [rcx+r11+115B0h]
0x14000d843  sub     r9, rax
0x14000d846  mov     eax, [r9-4]
0x14000d84a  shr     eax, cl
0x14000d84c  mov     [r8+8], r9
0x14000d850  lea     ecx, [rdx+rax]
0x14000d853  mov     [r8+30h], rcx
0x14000d857  movzx   ecx, byte ptr [r9]
0x14000d85b  and     ecx, 0Fh
0x14000d85e  movsx   rax, byte ptr [rcx+r11+115A0h]
0x14000d867  mov     cl, [rcx+r11+115B0h]
0x14000d86f  sub     r9, rax
0x14000d872  mov     eax, [r9-4]
0x14000d876  shr     eax, cl
0x14000d878  mov     [r8+8], r9
0x14000d87c  lea     ecx, [rdx+rax]
0x14000d87f  mov     [r8+38h], rcx
0x14000d883  retn
```
