# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x18000ac70`
- end: `0x18000ae04`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `404`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009af4`
- `0x180009ff8`
- `0x18000a858`

## callees

- `0x18000ac70`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r9
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r10
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r10
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r10
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r10
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
    v4 -= FH4::s_negLengthTab[v5];
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> FH4::s_shiftTab[v5];
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
    v4 -= FH4::s_negLengthTab[v7];
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> FH4::s_shiftTab[v7];
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  *((_QWORD *)this + 1) = v4 + 4;
  v9 = v3 & 0x30;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( (v3 & 0x30) == 0x20 )
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
      v14 = (char *)v8 - FH4::s_negLengthTab[v13];
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> FH4::s_shiftTab[v13]) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( (v3 & 0x30) == 0x20 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - FH4::s_negLengthTab[v17];
      v19 = *((_DWORD *)v18 - 1) >> FH4::s_shiftTab[v17];
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-FH4::s_negLengthTab[v20]];
      v22 = *((_DWORD *)v21 - 1) >> FH4::s_shiftTab[v20];
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x18000ac70  xor     eax, eax
0x18000ac72  lea     r11, cs:180000000h
0x18000ac79  mov     [rcx+18h], al
0x18000ac7c  xorps   xmm0, xmm0
0x18000ac7f  mov     [rcx+1Ch], rax
0x18000ac83  mov     r8, rcx
0x18000ac86  mov     [rcx+24h], rax
0x18000ac8a  movups  xmmword ptr [rcx+30h], xmm0
0x18000ac8e  mov     rax, [rcx+8]
0x18000ac92  mov     r9b, [rax]
0x18000ac95  lea     rdx, [rax+1]
0x18000ac99  mov     [rcx+18h], r9b
0x18000ac9d  mov     [rcx+8], rdx
0x18000aca1  test    r9b, 1
0x18000aca5  jz      short loc_18000ACCE
0x18000aca7  movzx   ecx, byte ptr [rdx]
0x18000acaa  and     ecx, 0Fh
0x18000acad  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000acb6  mov     cl, [rcx+r11+26800h]
0x18000acbe  sub     rdx, rax
0x18000acc1  mov     eax, [rdx-4]
0x18000acc4  shr     eax, cl
0x18000acc6  mov     [r8+1Ch], eax
0x18000acca  mov     [r8+8], rdx
0x18000acce  test    r9b, 2
0x18000acd2  jz      short loc_18000ACE2
0x18000acd4  mov     eax, [rdx]
0x18000acd6  add     rdx, 4
0x18000acda  mov     [r8+8], rdx
0x18000acde  mov     [r8+20h], eax
0x18000ace2  test    r9b, 4
0x18000ace6  jz      short loc_18000AD0F
0x18000ace8  movzx   ecx, byte ptr [rdx]
0x18000aceb  and     ecx, 0Fh
0x18000acee  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000acf7  mov     cl, [rcx+r11+26800h]
0x18000acff  sub     rdx, rax
0x18000ad02  mov     eax, [rdx-4]
0x18000ad05  shr     eax, cl
0x18000ad07  mov     [r8+24h], eax
0x18000ad0b  mov     [r8+8], rdx
0x18000ad0f  mov     eax, [rdx]
0x18000ad11  lea     r10, [rdx+4]
0x18000ad15  mov     [r8+28h], eax
0x18000ad19  mov     cl, 30h ; '0'
0x18000ad1b  mov     al, r9b
0x18000ad1e  mov     [r8+8], r10
0x18000ad22  and     al, cl
0x18000ad24  test    r9b, 8
0x18000ad28  jz      short loc_18000AD6A
0x18000ad2a  cmp     al, 10h
0x18000ad2c  jnz     short loc_18000AD3E
0x18000ad2e  movsxd  rcx, dword ptr [r10]
0x18000ad31  lea     rax, [r10+4]
0x18000ad35  mov     [r8+8], rax
0x18000ad39  mov     [r8+30h], rcx
0x18000ad3d  retn
0x18000ad3e  and     r9b, cl
0x18000ad41  cmp     r9b, 20h ; ' '
0x18000ad45  jnz     locret_18000AE03
0x18000ad4b  movsxd  rax, dword ptr [r10]
0x18000ad4e  lea     rdx, [r10+4]
0x18000ad52  mov     [r8+8], rdx
0x18000ad56  mov     [r8+30h], rax
0x18000ad5a  lea     rax, [rdx+4]
0x18000ad5e  movsxd  rcx, dword ptr [rdx]
0x18000ad61  mov     [r8+8], rax
0x18000ad65  jmp     loc_18000ADFF
0x18000ad6a  cmp     al, 10h
0x18000ad6c  jnz     short loc_18000AD9E
0x18000ad6e  movzx   ecx, byte ptr [r10]
0x18000ad72  and     ecx, 0Fh
0x18000ad75  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000ad7e  mov     cl, [rcx+r11+26800h]
0x18000ad86  sub     r10, rax
0x18000ad89  mov     eax, [r8+48h]
0x18000ad8d  mov     edx, [r10-4]
0x18000ad91  shr     edx, cl
0x18000ad93  add     eax, edx
0x18000ad95  mov     [r8+8], r10
0x18000ad99  mov     [r8+30h], rax
0x18000ad9d  retn
0x18000ad9e  and     r9b, cl
0x18000ada1  cmp     r9b, 20h ; ' '
0x18000ada5  jnz     short locret_18000AE03
0x18000ada7  movzx   ecx, byte ptr [r10]
0x18000adab  mov     edx, [r8+48h]
0x18000adaf  and     ecx, 0Fh
0x18000adb2  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000adbb  mov     cl, [rcx+r11+26800h]
0x18000adc3  sub     r10, rax
0x18000adc6  mov     eax, [r10-4]
0x18000adca  shr     eax, cl
0x18000adcc  mov     [r8+8], r10
0x18000add0  lea     ecx, [rdx+rax]
0x18000add3  mov     [r8+30h], rcx
0x18000add7  movzx   ecx, byte ptr [r10]
0x18000addb  and     ecx, 0Fh
0x18000adde  movsx   rax, byte ptr [rcx+r11+267F0h]
0x18000ade7  mov     cl, [rcx+r11+26800h]
0x18000adef  sub     r10, rax
0x18000adf2  mov     eax, [r10-4]
0x18000adf6  shr     eax, cl
0x18000adf8  mov     [r8+8], r10
0x18000adfc  lea     ecx, [rdx+rax]
0x18000adff  mov     [r8+38h], rcx
0x18000ae03  retn
```
