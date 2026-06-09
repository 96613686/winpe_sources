# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x180031214`
- end: `0x18003139c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f61c`
- `0x18002fdcc`
- `0x18003086c`
- `0x180030c8c`
- `0x180031d7c`
- `0x180031fb4`
- `0x180031fc4`

## callees

- `0x180031214`

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
0x180031214  xor     eax, eax
0x180031216  lea     r11, cs:180000000h
0x18003121d  mov     [rcx+18h], al
0x180031220  xorps   xmm0, xmm0
0x180031223  mov     [rcx+1Ch], rax
0x180031227  mov     r8, rcx
0x18003122a  mov     [rcx+24h], rax
0x18003122e  movups  xmmword ptr [rcx+30h], xmm0
0x180031232  mov     rax, [rcx+8]
0x180031236  mov     r10b, [rax]
0x180031239  lea     rdx, [rax+1]
0x18003123d  mov     [rcx+18h], r10b
0x180031241  mov     [rcx+8], rdx
0x180031245  test    r10b, 1
0x180031249  jz      short loc_180031272
0x18003124b  movzx   ecx, byte ptr [rdx]
0x18003124e  and     ecx, 0Fh
0x180031251  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x18003125a  mov     cl, [rcx+r11+6D0B0h]
0x180031262  sub     rdx, rax
0x180031265  mov     eax, [rdx-4]
0x180031268  shr     eax, cl
0x18003126a  mov     [r8+1Ch], eax
0x18003126e  mov     [r8+8], rdx
0x180031272  test    r10b, 2
0x180031276  jz      short loc_180031286
0x180031278  mov     eax, [rdx]
0x18003127a  add     rdx, 4
0x18003127e  mov     [r8+8], rdx
0x180031282  mov     [r8+20h], eax
0x180031286  test    r10b, 4
0x18003128a  jz      short loc_1800312B3
0x18003128c  movzx   ecx, byte ptr [rdx]
0x18003128f  and     ecx, 0Fh
0x180031292  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x18003129b  mov     cl, [rcx+r11+6D0B0h]
0x1800312a3  sub     rdx, rax
0x1800312a6  mov     eax, [rdx-4]
0x1800312a9  shr     eax, cl
0x1800312ab  mov     [r8+24h], eax
0x1800312af  mov     [r8+8], rdx
0x1800312b3  mov     eax, [rdx]
0x1800312b5  lea     r9, [rdx+4]
0x1800312b9  mov     [r8+28h], eax
0x1800312bd  mov     al, r10b
0x1800312c0  and     al, 30h
0x1800312c2  mov     [r8+8], r9
0x1800312c6  test    r10b, 8
0x1800312ca  jz      short loc_180031307
0x1800312cc  cmp     al, 10h
0x1800312ce  jnz     short loc_1800312E0
0x1800312d0  movsxd  rcx, dword ptr [r9]
0x1800312d3  lea     rax, [r9+4]
0x1800312d7  mov     [r8+8], rax
0x1800312db  mov     [r8+30h], rcx
0x1800312df  retn
0x1800312e0  cmp     al, 20h ; ' '
0x1800312e2  jnz     locret_18003139B
0x1800312e8  movsxd  rax, dword ptr [r9]
0x1800312eb  lea     rdx, [r9+4]
0x1800312ef  mov     [r8+8], rdx
0x1800312f3  mov     [r8+30h], rax
0x1800312f7  lea     rax, [rdx+4]
0x1800312fb  movsxd  rcx, dword ptr [rdx]
0x1800312fe  mov     [r8+8], rax
0x180031302  jmp     loc_180031397
0x180031307  cmp     al, 10h
0x180031309  jnz     short loc_18003133B
0x18003130b  movzx   ecx, byte ptr [r9]
0x18003130f  and     ecx, 0Fh
0x180031312  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x18003131b  mov     cl, [rcx+r11+6D0B0h]
0x180031323  sub     r9, rax
0x180031326  mov     eax, [r8+48h]
0x18003132a  mov     edx, [r9-4]
0x18003132e  shr     edx, cl
0x180031330  add     eax, edx
0x180031332  mov     [r8+8], r9
0x180031336  mov     [r8+30h], rax
0x18003133a  retn
0x18003133b  cmp     al, 20h ; ' '
0x18003133d  jnz     short locret_18003139B
0x18003133f  movzx   ecx, byte ptr [r9]
0x180031343  mov     edx, [r8+48h]
0x180031347  and     ecx, 0Fh
0x18003134a  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x180031353  mov     cl, [rcx+r11+6D0B0h]
0x18003135b  sub     r9, rax
0x18003135e  mov     eax, [r9-4]
0x180031362  shr     eax, cl
0x180031364  mov     [r8+8], r9
0x180031368  lea     ecx, [rdx+rax]
0x18003136b  mov     [r8+30h], rcx
0x18003136f  movzx   ecx, byte ptr [r9]
0x180031373  and     ecx, 0Fh
0x180031376  movsx   rax, byte ptr [rcx+r11+6D0A0h]
0x18003137f  mov     cl, [rcx+r11+6D0B0h]
0x180031387  sub     r9, rax
0x18003138a  mov     eax, [r9-4]
0x18003138e  shr     eax, cl
0x180031390  mov     [r8+8], r9
0x180031394  lea     ecx, [rdx+rax]
0x180031397  mov     [r8+38h], rcx
0x18003139b  retn
```
