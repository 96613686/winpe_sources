# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1800388e4`
- end: `0x180038a6c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003777c`
- `0x180037cc8`
- `0x18003852c`

## callees

- `0x1800388e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800388e4  xor     eax, eax
0x1800388e6  lea     r11, cs:180000000h
0x1800388ed  mov     [rcx+18h], al
0x1800388f0  xorps   xmm0, xmm0
0x1800388f3  mov     [rcx+1Ch], rax
0x1800388f7  mov     r8, rcx
0x1800388fa  mov     [rcx+24h], rax
0x1800388fe  movups  xmmword ptr [rcx+30h], xmm0
0x180038902  mov     rax, [rcx+8]
0x180038906  mov     r10b, [rax]
0x180038909  lea     rdx, [rax+1]
0x18003890d  mov     [rcx+18h], r10b
0x180038911  mov     [rcx+8], rdx
0x180038915  test    r10b, 1
0x180038919  jz      short loc_180038942
0x18003891b  movzx   ecx, byte ptr [rdx]
0x18003891e  and     ecx, 0Fh
0x180038921  movsx   rax, byte ptr [rcx+r11+46AA0h]
0x18003892a  mov     cl, [rcx+r11+46AB0h]
0x180038932  sub     rdx, rax
0x180038935  mov     eax, [rdx-4]
0x180038938  shr     eax, cl
0x18003893a  mov     [r8+1Ch], eax
0x18003893e  mov     [r8+8], rdx
0x180038942  test    r10b, 2
0x180038946  jz      short loc_180038956
0x180038948  mov     eax, [rdx]
0x18003894a  add     rdx, 4
0x18003894e  mov     [r8+8], rdx
0x180038952  mov     [r8+20h], eax
0x180038956  test    r10b, 4
0x18003895a  jz      short loc_180038983
0x18003895c  movzx   ecx, byte ptr [rdx]
0x18003895f  and     ecx, 0Fh
0x180038962  movsx   rax, byte ptr [rcx+r11+46AA0h]
0x18003896b  mov     cl, [rcx+r11+46AB0h]
0x180038973  sub     rdx, rax
0x180038976  mov     eax, [rdx-4]
0x180038979  shr     eax, cl
0x18003897b  mov     [r8+24h], eax
0x18003897f  mov     [r8+8], rdx
0x180038983  mov     eax, [rdx]
0x180038985  lea     r9, [rdx+4]
0x180038989  mov     [r8+28h], eax
0x18003898d  mov     al, r10b
0x180038990  and     al, 30h
0x180038992  mov     [r8+8], r9
0x180038996  test    r10b, 8
0x18003899a  jz      short loc_1800389D7
0x18003899c  cmp     al, 10h
0x18003899e  jnz     short loc_1800389B0
0x1800389a0  movsxd  rcx, dword ptr [r9]
0x1800389a3  lea     rax, [r9+4]
0x1800389a7  mov     [r8+8], rax
0x1800389ab  mov     [r8+30h], rcx
0x1800389af  retn
0x1800389b0  cmp     al, 20h ; ' '
0x1800389b2  jnz     locret_180038A6B
0x1800389b8  movsxd  rax, dword ptr [r9]
0x1800389bb  lea     rdx, [r9+4]
0x1800389bf  mov     [r8+8], rdx
0x1800389c3  mov     [r8+30h], rax
0x1800389c7  lea     rax, [rdx+4]
0x1800389cb  movsxd  rcx, dword ptr [rdx]
0x1800389ce  mov     [r8+8], rax
0x1800389d2  jmp     loc_180038A67
0x1800389d7  cmp     al, 10h
0x1800389d9  jnz     short loc_180038A0B
0x1800389db  movzx   ecx, byte ptr [r9]
0x1800389df  and     ecx, 0Fh
0x1800389e2  movsx   rax, byte ptr [rcx+r11+46AA0h]
0x1800389eb  mov     cl, [rcx+r11+46AB0h]
0x1800389f3  sub     r9, rax
0x1800389f6  mov     eax, [r8+48h]
0x1800389fa  mov     edx, [r9-4]
0x1800389fe  shr     edx, cl
0x180038a00  add     eax, edx
0x180038a02  mov     [r8+8], r9
0x180038a06  mov     [r8+30h], rax
0x180038a0a  retn
0x180038a0b  cmp     al, 20h ; ' '
0x180038a0d  jnz     short locret_180038A6B
0x180038a0f  movzx   ecx, byte ptr [r9]
0x180038a13  mov     edx, [r8+48h]
0x180038a17  and     ecx, 0Fh
0x180038a1a  movsx   rax, byte ptr [rcx+r11+46AA0h]
0x180038a23  mov     cl, [rcx+r11+46AB0h]
0x180038a2b  sub     r9, rax
0x180038a2e  mov     eax, [r9-4]
0x180038a32  shr     eax, cl
0x180038a34  mov     [r8+8], r9
0x180038a38  lea     ecx, [rdx+rax]
0x180038a3b  mov     [r8+30h], rcx
0x180038a3f  movzx   ecx, byte ptr [r9]
0x180038a43  and     ecx, 0Fh
0x180038a46  movsx   rax, byte ptr [rcx+r11+46AA0h]
0x180038a4f  mov     cl, [rcx+r11+46AB0h]
0x180038a57  sub     r9, rax
0x180038a5a  mov     eax, [r9-4]
0x180038a5e  shr     eax, cl
0x180038a60  mov     [r8+8], r9
0x180038a64  lea     ecx, [rdx+rax]
0x180038a67  mov     [r8+38h], rcx
0x180038a6b  retn
```
