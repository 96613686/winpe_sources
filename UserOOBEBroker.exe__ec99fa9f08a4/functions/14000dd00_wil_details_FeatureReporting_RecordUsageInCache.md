# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000dd00`
- end: `0x14000dfda`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c778`

## callees

- `0x14000dd00`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 v11; // edx
  int v12; // ebx
  signed __int32 v13; // r9d
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  BOOL v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22; // eax
  signed __int32 v23; // edx
  BOOL v24; // ebp
  unsigned int v25; // eax
  int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  signed __int32 v29; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v23 = *a2;
      v24 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v25 = v23 | 1;
        if ( (((v23 | 1u) >> 14) & 1) != v24 )
        {
          if ( ((v25 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v25 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v25 = v23 & 0xFFFFC01E | 1;
          }
          v26 = 0;
          if ( a3 == 4 )
            v26 = 0x4000;
          v25 = v25 & 0xFFFFBFFF | v26;
        }
        v27 = (v25 >> 5) & 0x1FF;
        v28 = v27 + 1;
        if ( v27 + 1 > 0x1FF || v28 < v27 )
        {
          LOWORD(v28) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v27;
        }
        v29 = _InterlockedCompareExchange(
                a2,
                v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v28)) & 0x3FE0,
                v23);
        if ( v23 == v29 )
          break;
        v23 = v29;
      }
      *(_DWORD *)a1 = (v23 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v15 = *a2;
      v16 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v17 = v15 | 1;
        if ( (((v15 | 1u) >> 22) & 1) != v16 )
        {
          if ( ((v17 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v17 >> 15) & 0x7F;
            v18 = 5;
            if ( a3 != 1 )
              v18 = 1;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v19 = 0;
          if ( a3 == 5 )
            v19 = 0x400000;
          v17 = v17 & 0xFFBFFFFF | v19;
        }
        v20 = (v17 >> 15) & 0x7F;
        v21 = v20 + 1;
        if ( v20 + 1 > 0x7F || v21 < v20 )
        {
          v21 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v20;
        }
        v22 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v21 << 15)) & 0x3F8000, v15);
        if ( v15 == v22 )
          break;
        v15 = v22;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 >= 64 )
      goto LABEL_16;
    v7 = *((_DWORD *)a2 + 1);
    do
    {
      v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
      *(_DWORD *)(a1 + 16) = v8;
      v9 = v7;
      v7 = _InterlockedCompareExchange(
             a2 + 1,
             v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
             v7);
    }
    while ( v9 != v7 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v10 = 0;
  switch ( a3 )
  {
    case 2:
      v10 = 2;
      break;
    case 3:
      v10 = 8;
      break;
    case 6:
      v10 = 4;
      break;
    case 7:
      v10 = 16;
      break;
  }
  v11 = *a2;
  v12 = 1;
  while ( 1 )
  {
    v13 = v11 | v10 | 1;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    if ( (v11 | v10) == v11 )
      v13 = v11 | v10;
    v14 = _InterlockedCompareExchange(a2, v13, v11);
    if ( v11 == v14 )
      break;
    v11 = v14;
  }
  if ( (v13 & 1) == 0 || (v11 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x14000dd00  push    rbx
0x14000dd02  push    rbp
0x14000dd03  push    rsi
0x14000dd04  push    rdi
0x14000dd05  xor     eax, eax
0x14000dd07  xorps   xmm0, xmm0
0x14000dd0a  mov     r11d, r8d
0x14000dd0d  mov     rsi, rdx
0x14000dd10  mov     r10, rcx
0x14000dd13  mov     r9d, r8d
0x14000dd16  movups  xmmword ptr [rcx], xmm0
0x14000dd19  mov     [rcx+10h], rax
0x14000dd1d  test    r8d, r8d
0x14000dd20  jz      loc_14000DF04
0x14000dd26  sub     r9d, 1
0x14000dd2a  jz      loc_14000DE4B
0x14000dd30  sub     r9d, 1
0x14000dd34  jz      loc_14000DDD2
0x14000dd3a  sub     r9d, 1
0x14000dd3e  jz      loc_14000DDD2
0x14000dd44  sub     r9d, 1
0x14000dd48  jz      loc_14000DF04
0x14000dd4e  sub     r9d, 1
0x14000dd52  jz      loc_14000DE4B
0x14000dd58  sub     r9d, 1
0x14000dd5c  jz      short loc_14000DDD2
0x14000dd5e  cmp     r9d, 1
0x14000dd62  jz      short loc_14000DDD2
0x14000dd64  add     r8d, 0FFFFFEC0h
0x14000dd6b  lea     ebx, [rax+1]
0x14000dd6e  cmp     r8d, 40h ; '@'
0x14000dd72  jge     short loc_14000DDBD
0x14000dd74  mov     eax, [rdx+4]
0x14000dd77  lea     ecx, [rbx+0Fh]
0x14000dd7a  mov     r9d, r8d
0x14000dd7d  shl     r9d, 5
0x14000dd81  test    cl, al
0x14000dd83  jz      short loc_14000DD96
0x14000dd85  mov     edx, eax
0x14000dd87  shr     edx, 5
0x14000dd8a  and     edx, 3Fh
0x14000dd8d  cmp     edx, r8d
0x14000dd90  jnz     short loc_14000DD96
0x14000dd92  mov     edx, ebx
0x14000dd94  jmp     short loc_14000DD98
0x14000dd96  xor     edx, edx
0x14000dd98  mov     [r10+10h], edx
0x14000dd9c  mov     edx, r9d
0x14000dd9f  xor     edx, eax
0x14000dda1  and     edx, 7E0h
0x14000dda7  xor     edx, eax
0x14000dda9  or      edx, ecx
0x14000ddab  lock cmpxchg [rsi+4], edx
0x14000ddb0  jnz     short loc_14000DD81
0x14000ddb2  cmp     dword ptr [r10+10h], 0
0x14000ddb7  jnz     loc_14000DFD2
0x14000ddbd  mov     [r10+8], r11d
0x14000ddc1  mov     [r10+4], ebx
0x14000ddc5  mov     dword ptr [r10+0Ch], 0
0x14000ddcd  jmp     loc_14000DFD2
0x14000ddd2  xor     ecx, ecx
0x14000ddd4  sub     r11d, 2
0x14000ddd8  jz      short loc_14000DE00
0x14000ddda  sub     r11d, 1
0x14000ddde  jz      short loc_14000DDF9
0x14000dde0  sub     r11d, 3
0x14000dde4  jz      short loc_14000DDF2
0x14000dde6  cmp     r11d, 1
0x14000ddea  jnz     short loc_14000DE05
0x14000ddec  lea     ecx, [r11+0Fh]
0x14000ddf0  jmp     short loc_14000DE05
0x14000ddf2  mov     ecx, 4
0x14000ddf7  jmp     short loc_14000DE05
0x14000ddf9  mov     ecx, 8
0x14000ddfe  jmp     short loc_14000DE05
0x14000de00  mov     ecx, 2
0x14000de05  mov     edx, [rdx]
0x14000de07  mov     ebx, 1
0x14000de0c  xor     eax, eax
0x14000de0e  mov     r8d, ecx
0x14000de11  or      r8d, edx
0x14000de14  cmp     r8d, edx
0x14000de17  mov     r9d, r8d
0x14000de1a  setz    al
0x14000de1d  or      r9d, ebx
0x14000de20  cmp     r8d, edx
0x14000de23  mov     [r10+10h], eax
0x14000de27  mov     eax, edx
0x14000de29  cmovz   r9d, r8d
0x14000de2d  lock cmpxchg [rsi], r9d
0x14000de32  jz      short loc_14000DE38
0x14000de34  mov     edx, eax
0x14000de36  jmp     short loc_14000DE0C
0x14000de38  test    bl, r9b
0x14000de3b  jz      short loc_14000DE41
0x14000de3d  test    bl, dl
0x14000de3f  jz      short loc_14000DE43
0x14000de41  xor     ebx, ebx
0x14000de43  mov     [r10], ebx
0x14000de46  jmp     loc_14000DFD2
0x14000de4b  mov     ecx, [rdx]
0x14000de4d  xor     r9d, r9d
0x14000de50  cmp     r11d, 5
0x14000de54  mov     ebx, 1
0x14000de59  setz    r9b
0x14000de5d  mov     eax, ecx
0x14000de5f  mov     dword ptr [r10+4], 0
0x14000de67  or      eax, ebx
0x14000de69  mov     edx, eax
0x14000de6b  shr     edx, 16h
0x14000de6e  and     edx, ebx
0x14000de70  cmp     edx, r9d
0x14000de73  jz      short loc_14000DEB5
0x14000de75  mov     r8d, eax
0x14000de78  shr     r8d, 0Fh
0x14000de7c  and     r8d, 7Fh
0x14000de80  jbe     short loc_14000DE9A
0x14000de82  cmp     r11d, ebx
0x14000de85  mov     [r10+4], r8d
0x14000de89  mov     edx, 5
0x14000de8e  cmovnz  edx, ebx
0x14000de91  and     eax, 0FFC07FFFh
0x14000de96  mov     [r10+8], edx
0x14000de9a  xor     r8d, r8d
0x14000de9d  mov     edx, 400000h
0x14000dea2  cmp     r11d, 5
0x14000dea6  cmovz   r8d, edx
0x14000deaa  mov     edx, eax
0x14000deac  btr     edx, 16h
0x14000deb0  mov     eax, r8d
0x14000deb3  or      eax, edx
0x14000deb5  mov     edx, eax
0x14000deb7  shr     edx, 0Fh
0x14000deba  and     edx, 7Fh
0x14000debd  lea     r8d, [rdx+1]
0x14000dec1  cmp     r8d, 7Fh
0x14000dec5  ja      short loc_14000DECC
0x14000dec7  cmp     r8d, edx
0x14000deca  jnb     short loc_14000DED7
0x14000decc  mov     r8d, ebx
0x14000decf  mov     [r10+8], r11d
0x14000ded3  mov     [r10+4], edx
0x14000ded7  shl     r8d, 0Fh
0x14000dedb  xor     r8d, eax
0x14000dede  and     r8d, 3F8000h
0x14000dee5  xor     r8d, eax
0x14000dee8  mov     eax, ecx
0x14000deea  lock cmpxchg [rsi], r8d
0x14000deef  jz      short loc_14000DEF8
0x14000def1  mov     ecx, eax
0x14000def3  jmp     loc_14000DE5D
0x14000def8  not     ecx
0x14000defa  and     ecx, ebx
0x14000defc  mov     [r10], ecx
0x14000deff  jmp     loc_14000DFCA
0x14000df04  mov     edx, [rdx]
0x14000df06  xor     ebp, ebp
0x14000df08  lea     ecx, [rbp+4]
0x14000df0b  cmp     r11d, ecx
0x14000df0e  lea     ebx, [rcx-3]
0x14000df11  setz    bpl
0x14000df15  mov     eax, edx
0x14000df17  mov     dword ptr [r10+4], 0
0x14000df1f  or      eax, ebx
0x14000df21  mov     r8d, eax
0x14000df24  shr     r8d, 0Eh
0x14000df28  and     r8d, ebx
0x14000df2b  cmp     r8d, ebp
0x14000df2e  jz      short loc_14000DF77
0x14000df30  mov     edi, eax
0x14000df32  shr     edi, 5
0x14000df35  and     edi, 1FFh
0x14000df3b  jbe     short loc_14000DF59
0x14000df3d  mov     r8d, r11d
0x14000df40  mov     [r10+4], edi
0x14000df44  neg     r8d
0x14000df47  sbb     r9d, r9d
0x14000df4a  not     r9d
0x14000df4d  and     r9d, ecx
0x14000df50  mov     [r10+8], r9d
0x14000df54  and     eax, 0FFFFC01Fh
0x14000df59  xor     r9d, r9d
0x14000df5c  mov     r8d, 4000h
0x14000df62  cmp     r11d, ecx
0x14000df65  cmovz   r9d, r8d
0x14000df69  mov     r8d, eax
0x14000df6c  btr     r8d, 0Eh
0x14000df71  mov     eax, r9d
0x14000df74  or      eax, r8d
0x14000df77  mov     r8d, eax
0x14000df7a  shr     r8d, 5
0x14000df7e  and     r8d, 1FFh
0x14000df85  lea     r9d, [r8+1]
0x14000df89  cmp     r9d, 1FFh
0x14000df90  ja      short loc_14000DF97
0x14000df92  cmp     r9d, r8d
0x14000df95  jnb     short loc_14000DFA2
0x14000df97  mov     r9d, ebx
0x14000df9a  mov     [r10+8], r11d
0x14000df9e  mov     [r10+4], r8d
0x14000dfa2  shl     r9d, 5
0x14000dfa6  xor     r9d, eax
0x14000dfa9  and     r9d, 3FE0h
0x14000dfb0  xor     r9d, eax
0x14000dfb3  mov     eax, edx
0x14000dfb5  lock cmpxchg [rsi], r9d
0x14000dfba  jz      short loc_14000DFC3
0x14000dfbc  mov     edx, eax
0x14000dfbe  jmp     loc_14000DF15
0x14000dfc3  not     edx
0x14000dfc5  and     edx, ebx
0x14000dfc7  mov     [r10], edx
0x14000dfca  mov     dword ptr [r10+10h], 0
0x14000dfd2  mov     rax, r10
0x14000dfd5  pop     rdi
0x14000dfd6  pop     rsi
0x14000dfd7  pop     rbp
0x14000dfd8  pop     rbx
0x14000dfd9  retn
```
