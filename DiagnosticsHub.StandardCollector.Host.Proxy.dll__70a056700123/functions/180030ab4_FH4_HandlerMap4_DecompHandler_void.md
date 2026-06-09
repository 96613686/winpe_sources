# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x180030ab4`
- end: `0x180030c3c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002eebc`
- `0x18002f66c`
- `0x18003010c`
- `0x18003052c`
- `0x18003161c`
- `0x180031854`
- `0x180031864`

## callees

- `0x180030ab4`

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
0x180030ab4  xor     eax, eax
0x180030ab6  lea     r11, cs:180000000h
0x180030abd  mov     [rcx+18h], al
0x180030ac0  xorps   xmm0, xmm0
0x180030ac3  mov     [rcx+1Ch], rax
0x180030ac7  mov     r8, rcx
0x180030aca  mov     [rcx+24h], rax
0x180030ace  movups  xmmword ptr [rcx+30h], xmm0
0x180030ad2  mov     rax, [rcx+8]
0x180030ad6  mov     r10b, [rax]
0x180030ad9  lea     rdx, [rax+1]
0x180030add  mov     [rcx+18h], r10b
0x180030ae1  mov     [rcx+8], rdx
0x180030ae5  test    r10b, 1
0x180030ae9  jz      short loc_180030B12
0x180030aeb  movzx   ecx, byte ptr [rdx]
0x180030aee  and     ecx, 0Fh
0x180030af1  movsx   rax, byte ptr [rcx+r11+699C0h]
0x180030afa  mov     cl, [rcx+r11+699D0h]
0x180030b02  sub     rdx, rax
0x180030b05  mov     eax, [rdx-4]
0x180030b08  shr     eax, cl
0x180030b0a  mov     [r8+1Ch], eax
0x180030b0e  mov     [r8+8], rdx
0x180030b12  test    r10b, 2
0x180030b16  jz      short loc_180030B26
0x180030b18  mov     eax, [rdx]
0x180030b1a  add     rdx, 4
0x180030b1e  mov     [r8+8], rdx
0x180030b22  mov     [r8+20h], eax
0x180030b26  test    r10b, 4
0x180030b2a  jz      short loc_180030B53
0x180030b2c  movzx   ecx, byte ptr [rdx]
0x180030b2f  and     ecx, 0Fh
0x180030b32  movsx   rax, byte ptr [rcx+r11+699C0h]
0x180030b3b  mov     cl, [rcx+r11+699D0h]
0x180030b43  sub     rdx, rax
0x180030b46  mov     eax, [rdx-4]
0x180030b49  shr     eax, cl
0x180030b4b  mov     [r8+24h], eax
0x180030b4f  mov     [r8+8], rdx
0x180030b53  mov     eax, [rdx]
0x180030b55  lea     r9, [rdx+4]
0x180030b59  mov     [r8+28h], eax
0x180030b5d  mov     al, r10b
0x180030b60  and     al, 30h
0x180030b62  mov     [r8+8], r9
0x180030b66  test    r10b, 8
0x180030b6a  jz      short loc_180030BA7
0x180030b6c  cmp     al, 10h
0x180030b6e  jnz     short loc_180030B80
0x180030b70  movsxd  rcx, dword ptr [r9]
0x180030b73  lea     rax, [r9+4]
0x180030b77  mov     [r8+8], rax
0x180030b7b  mov     [r8+30h], rcx
0x180030b7f  retn
0x180030b80  cmp     al, 20h ; ' '
0x180030b82  jnz     locret_180030C3B
0x180030b88  movsxd  rax, dword ptr [r9]
0x180030b8b  lea     rdx, [r9+4]
0x180030b8f  mov     [r8+8], rdx
0x180030b93  mov     [r8+30h], rax
0x180030b97  lea     rax, [rdx+4]
0x180030b9b  movsxd  rcx, dword ptr [rdx]
0x180030b9e  mov     [r8+8], rax
0x180030ba2  jmp     loc_180030C37
0x180030ba7  cmp     al, 10h
0x180030ba9  jnz     short loc_180030BDB
0x180030bab  movzx   ecx, byte ptr [r9]
0x180030baf  and     ecx, 0Fh
0x180030bb2  movsx   rax, byte ptr [rcx+r11+699C0h]
0x180030bbb  mov     cl, [rcx+r11+699D0h]
0x180030bc3  sub     r9, rax
0x180030bc6  mov     eax, [r8+48h]
0x180030bca  mov     edx, [r9-4]
0x180030bce  shr     edx, cl
0x180030bd0  add     eax, edx
0x180030bd2  mov     [r8+8], r9
0x180030bd6  mov     [r8+30h], rax
0x180030bda  retn
0x180030bdb  cmp     al, 20h ; ' '
0x180030bdd  jnz     short locret_180030C3B
0x180030bdf  movzx   ecx, byte ptr [r9]
0x180030be3  mov     edx, [r8+48h]
0x180030be7  and     ecx, 0Fh
0x180030bea  movsx   rax, byte ptr [rcx+r11+699C0h]
0x180030bf3  mov     cl, [rcx+r11+699D0h]
0x180030bfb  sub     r9, rax
0x180030bfe  mov     eax, [r9-4]
0x180030c02  shr     eax, cl
0x180030c04  mov     [r8+8], r9
0x180030c08  lea     ecx, [rdx+rax]
0x180030c0b  mov     [r8+30h], rcx
0x180030c0f  movzx   ecx, byte ptr [r9]
0x180030c13  and     ecx, 0Fh
0x180030c16  movsx   rax, byte ptr [rcx+r11+699C0h]
0x180030c1f  mov     cl, [rcx+r11+699D0h]
0x180030c27  sub     r9, rax
0x180030c2a  mov     eax, [r9-4]
0x180030c2e  shr     eax, cl
0x180030c30  mov     [r8+8], r9
0x180030c34  lea     ecx, [rdx+rax]
0x180030c37  mov     [r8+38h], rcx
0x180030c3b  retn
```
