# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x18000a774`
- end: `0x18000a8fc`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800095ac`
- `0x180009af8`
- `0x18000a35c`

## callees

- `0x18000a774`

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
0x18000a774  xor     eax, eax
0x18000a776  lea     r11, cs:180000000h
0x18000a77d  mov     [rcx+18h], al
0x18000a780  xorps   xmm0, xmm0
0x18000a783  mov     [rcx+1Ch], rax
0x18000a787  mov     r8, rcx
0x18000a78a  mov     [rcx+24h], rax
0x18000a78e  movups  xmmword ptr [rcx+30h], xmm0
0x18000a792  mov     rax, [rcx+8]
0x18000a796  mov     r10b, [rax]
0x18000a799  lea     rdx, [rax+1]
0x18000a79d  mov     [rcx+18h], r10b
0x18000a7a1  mov     [rcx+8], rdx
0x18000a7a5  test    r10b, 1
0x18000a7a9  jz      short loc_18000A7D2
0x18000a7ab  movzx   ecx, byte ptr [rdx]
0x18000a7ae  and     ecx, 0Fh
0x18000a7b1  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000a7ba  mov     cl, [rcx+r11+0D5F8h]
0x18000a7c2  sub     rdx, rax
0x18000a7c5  mov     eax, [rdx-4]
0x18000a7c8  shr     eax, cl
0x18000a7ca  mov     [r8+1Ch], eax
0x18000a7ce  mov     [r8+8], rdx
0x18000a7d2  test    r10b, 2
0x18000a7d6  jz      short loc_18000A7E6
0x18000a7d8  mov     eax, [rdx]
0x18000a7da  add     rdx, 4
0x18000a7de  mov     [r8+8], rdx
0x18000a7e2  mov     [r8+20h], eax
0x18000a7e6  test    r10b, 4
0x18000a7ea  jz      short loc_18000A813
0x18000a7ec  movzx   ecx, byte ptr [rdx]
0x18000a7ef  and     ecx, 0Fh
0x18000a7f2  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000a7fb  mov     cl, [rcx+r11+0D5F8h]
0x18000a803  sub     rdx, rax
0x18000a806  mov     eax, [rdx-4]
0x18000a809  shr     eax, cl
0x18000a80b  mov     [r8+24h], eax
0x18000a80f  mov     [r8+8], rdx
0x18000a813  mov     eax, [rdx]
0x18000a815  lea     r9, [rdx+4]
0x18000a819  mov     [r8+28h], eax
0x18000a81d  mov     al, r10b
0x18000a820  and     al, 30h
0x18000a822  mov     [r8+8], r9
0x18000a826  test    r10b, 8
0x18000a82a  jz      short loc_18000A867
0x18000a82c  cmp     al, 10h
0x18000a82e  jnz     short loc_18000A840
0x18000a830  movsxd  rcx, dword ptr [r9]
0x18000a833  lea     rax, [r9+4]
0x18000a837  mov     [r8+8], rax
0x18000a83b  mov     [r8+30h], rcx
0x18000a83f  retn
0x18000a840  cmp     al, 20h ; ' '
0x18000a842  jnz     locret_18000A8FB
0x18000a848  movsxd  rax, dword ptr [r9]
0x18000a84b  lea     rdx, [r9+4]
0x18000a84f  mov     [r8+8], rdx
0x18000a853  mov     [r8+30h], rax
0x18000a857  lea     rax, [rdx+4]
0x18000a85b  movsxd  rcx, dword ptr [rdx]
0x18000a85e  mov     [r8+8], rax
0x18000a862  jmp     loc_18000A8F7
0x18000a867  cmp     al, 10h
0x18000a869  jnz     short loc_18000A89B
0x18000a86b  movzx   ecx, byte ptr [r9]
0x18000a86f  and     ecx, 0Fh
0x18000a872  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000a87b  mov     cl, [rcx+r11+0D5F8h]
0x18000a883  sub     r9, rax
0x18000a886  mov     eax, [r8+48h]
0x18000a88a  mov     edx, [r9-4]
0x18000a88e  shr     edx, cl
0x18000a890  add     eax, edx
0x18000a892  mov     [r8+8], r9
0x18000a896  mov     [r8+30h], rax
0x18000a89a  retn
0x18000a89b  cmp     al, 20h ; ' '
0x18000a89d  jnz     short locret_18000A8FB
0x18000a89f  movzx   ecx, byte ptr [r9]
0x18000a8a3  mov     edx, [r8+48h]
0x18000a8a7  and     ecx, 0Fh
0x18000a8aa  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000a8b3  mov     cl, [rcx+r11+0D5F8h]
0x18000a8bb  sub     r9, rax
0x18000a8be  mov     eax, [r9-4]
0x18000a8c2  shr     eax, cl
0x18000a8c4  mov     [r8+8], r9
0x18000a8c8  lea     ecx, [rdx+rax]
0x18000a8cb  mov     [r8+30h], rcx
0x18000a8cf  movzx   ecx, byte ptr [r9]
0x18000a8d3  and     ecx, 0Fh
0x18000a8d6  movsx   rax, byte ptr [rcx+r11+0D5E8h]
0x18000a8df  mov     cl, [rcx+r11+0D5F8h]
0x18000a8e7  sub     r9, rax
0x18000a8ea  mov     eax, [r9-4]
0x18000a8ee  shr     eax, cl
0x18000a8f0  mov     [r8+8], r9
0x18000a8f4  lea     ecx, [rdx+rax]
0x18000a8f7  mov     [r8+38h], rcx
0x18000a8fb  retn
```
