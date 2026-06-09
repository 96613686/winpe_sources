# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000dc30`
- end: `0x14000df02`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e034`

## callees

- `0x14000dc30`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

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
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x14000dc30  push    rbx
0x14000dc32  push    rbp
0x14000dc33  push    rsi
0x14000dc34  push    rdi
0x14000dc35  xor     eax, eax
0x14000dc37  xorps   xmm0, xmm0
0x14000dc3a  mov     r10, rcx
0x14000dc3d  mov     edi, r9d
0x14000dc40  mov     r11d, r8d
0x14000dc43  mov     rsi, rdx
0x14000dc46  movups  xmmword ptr [rcx], xmm0
0x14000dc49  mov     [rcx+10h], rax
0x14000dc4d  mov     ecx, r8d
0x14000dc50  test    r8d, r8d
0x14000dc53  jz      loc_14000DE2C
0x14000dc59  sub     ecx, 1
0x14000dc5c  jz      loc_14000DD73
0x14000dc62  sub     ecx, 1
0x14000dc65  jz      loc_14000DCFA
0x14000dc6b  sub     ecx, 1
0x14000dc6e  jz      loc_14000DCFA
0x14000dc74  sub     ecx, 1
0x14000dc77  jz      loc_14000DE2C
0x14000dc7d  sub     ecx, 1
0x14000dc80  jz      loc_14000DD73
0x14000dc86  sub     ecx, 1
0x14000dc89  jz      short loc_14000DCFA
0x14000dc8b  cmp     ecx, 1
0x14000dc8e  jz      short loc_14000DCFA
0x14000dc90  add     r8d, 0FFFFFEC0h
0x14000dc97  lea     ebx, [rax+1]
0x14000dc9a  cmp     r8d, 40h ; '@'
0x14000dc9e  jge     short loc_14000DCE9
0x14000dca0  mov     eax, [rdx+4]
0x14000dca3  lea     ecx, [rbx+0Fh]
0x14000dca6  mov     r9d, r8d
0x14000dca9  shl     r9d, 5
0x14000dcad  test    cl, al
0x14000dcaf  jz      short loc_14000DCC2
0x14000dcb1  mov     edx, eax
0x14000dcb3  shr     edx, 5
0x14000dcb6  and     edx, 3Fh
0x14000dcb9  cmp     edx, r8d
0x14000dcbc  jnz     short loc_14000DCC2
0x14000dcbe  mov     edx, ebx
0x14000dcc0  jmp     short loc_14000DCC4
0x14000dcc2  xor     edx, edx
0x14000dcc4  mov     [r10+10h], edx
0x14000dcc8  mov     edx, r9d
0x14000dccb  xor     edx, eax
0x14000dccd  and     edx, 7E0h
0x14000dcd3  xor     edx, eax
0x14000dcd5  or      edx, ecx
0x14000dcd7  lock cmpxchg [rsi+4], edx
0x14000dcdc  jnz     short loc_14000DCAD
0x14000dcde  cmp     dword ptr [r10+10h], 0
0x14000dce3  jnz     loc_14000DEFA
0x14000dce9  mov     [r10+8], r11d
0x14000dced  mov     [r10+4], ebx
0x14000dcf1  mov     [r10+0Ch], edi
0x14000dcf5  jmp     loc_14000DEFA
0x14000dcfa  xor     ecx, ecx
0x14000dcfc  sub     r11d, 2
0x14000dd00  jz      short loc_14000DD28
0x14000dd02  sub     r11d, 1
0x14000dd06  jz      short loc_14000DD21
0x14000dd08  sub     r11d, 3
0x14000dd0c  jz      short loc_14000DD1A
0x14000dd0e  cmp     r11d, 1
0x14000dd12  jnz     short loc_14000DD2D
0x14000dd14  lea     ecx, [r11+0Fh]
0x14000dd18  jmp     short loc_14000DD2D
0x14000dd1a  mov     ecx, 4
0x14000dd1f  jmp     short loc_14000DD2D
0x14000dd21  mov     ecx, 8
0x14000dd26  jmp     short loc_14000DD2D
0x14000dd28  mov     ecx, 2
0x14000dd2d  mov     edx, [rdx]
0x14000dd2f  mov     ebx, 1
0x14000dd34  xor     eax, eax
0x14000dd36  mov     r8d, ecx
0x14000dd39  or      r8d, edx
0x14000dd3c  cmp     r8d, edx
0x14000dd3f  mov     r9d, r8d
0x14000dd42  setz    al
0x14000dd45  or      r9d, ebx
0x14000dd48  cmp     r8d, edx
0x14000dd4b  mov     [r10+10h], eax
0x14000dd4f  mov     eax, edx
0x14000dd51  cmovz   r9d, r8d
0x14000dd55  lock cmpxchg [rsi], r9d
0x14000dd5a  jz      short loc_14000DD60
0x14000dd5c  mov     edx, eax
0x14000dd5e  jmp     short loc_14000DD34
0x14000dd60  test    bl, r9b
0x14000dd63  jz      short loc_14000DD69
0x14000dd65  test    bl, dl
0x14000dd67  jz      short loc_14000DD6B
0x14000dd69  xor     ebx, ebx
0x14000dd6b  mov     [r10], ebx
0x14000dd6e  jmp     loc_14000DEFA
0x14000dd73  mov     ecx, [rdx]
0x14000dd75  xor     r9d, r9d
0x14000dd78  cmp     r11d, 5
0x14000dd7c  mov     ebx, 1
0x14000dd81  setz    r9b
0x14000dd85  mov     eax, ecx
0x14000dd87  mov     dword ptr [r10+4], 0
0x14000dd8f  or      eax, ebx
0x14000dd91  mov     edx, eax
0x14000dd93  shr     edx, 16h
0x14000dd96  and     edx, ebx
0x14000dd98  cmp     edx, r9d
0x14000dd9b  jz      short loc_14000DDDD
0x14000dd9d  mov     r8d, eax
0x14000dda0  shr     r8d, 0Fh
0x14000dda4  and     r8d, 7Fh
0x14000dda8  jbe     short loc_14000DDC2
0x14000ddaa  cmp     r11d, ebx
0x14000ddad  mov     [r10+4], r8d
0x14000ddb1  mov     edx, 5
0x14000ddb6  cmovnz  edx, ebx
0x14000ddb9  and     eax, 0FFC07FFFh
0x14000ddbe  mov     [r10+8], edx
0x14000ddc2  xor     r8d, r8d
0x14000ddc5  mov     edx, 400000h
0x14000ddca  cmp     r11d, 5
0x14000ddce  cmovz   r8d, edx
0x14000ddd2  mov     edx, eax
0x14000ddd4  btr     edx, 16h
0x14000ddd8  mov     eax, r8d
0x14000dddb  or      eax, edx
0x14000dddd  mov     edx, eax
0x14000dddf  shr     edx, 0Fh
0x14000dde2  and     edx, 7Fh
0x14000dde5  lea     r8d, [rdx+1]
0x14000dde9  cmp     r8d, 7Fh
0x14000dded  ja      short loc_14000DDF4
0x14000ddef  cmp     r8d, edx
0x14000ddf2  jnb     short loc_14000DDFF
0x14000ddf4  mov     r8d, ebx
0x14000ddf7  mov     [r10+8], r11d
0x14000ddfb  mov     [r10+4], edx
0x14000ddff  shl     r8d, 0Fh
0x14000de03  xor     r8d, eax
0x14000de06  and     r8d, 3F8000h
0x14000de0d  xor     r8d, eax
0x14000de10  mov     eax, ecx
0x14000de12  lock cmpxchg [rsi], r8d
0x14000de17  jz      short loc_14000DE20
0x14000de19  mov     ecx, eax
0x14000de1b  jmp     loc_14000DD85
0x14000de20  not     ecx
0x14000de22  and     ecx, ebx
0x14000de24  mov     [r10], ecx
0x14000de27  jmp     loc_14000DEF2
0x14000de2c  mov     edx, [rdx]
0x14000de2e  xor     ebp, ebp
0x14000de30  lea     ecx, [rbp+4]
0x14000de33  cmp     r11d, ecx
0x14000de36  lea     ebx, [rcx-3]
0x14000de39  setz    bpl
0x14000de3d  mov     eax, edx
0x14000de3f  mov     dword ptr [r10+4], 0
0x14000de47  or      eax, ebx
0x14000de49  mov     r8d, eax
0x14000de4c  shr     r8d, 0Eh
0x14000de50  and     r8d, ebx
0x14000de53  cmp     r8d, ebp
0x14000de56  jz      short loc_14000DE9F
0x14000de58  mov     edi, eax
0x14000de5a  shr     edi, 5
0x14000de5d  and     edi, 1FFh
0x14000de63  jbe     short loc_14000DE81
0x14000de65  mov     r8d, r11d
0x14000de68  mov     [r10+4], edi
0x14000de6c  neg     r8d
0x14000de6f  sbb     r9d, r9d
0x14000de72  not     r9d
0x14000de75  and     r9d, ecx
0x14000de78  mov     [r10+8], r9d
0x14000de7c  and     eax, 0FFFFC01Fh
0x14000de81  xor     r9d, r9d
0x14000de84  mov     r8d, 4000h
0x14000de8a  cmp     r11d, ecx
0x14000de8d  cmovz   r9d, r8d
0x14000de91  mov     r8d, eax
0x14000de94  btr     r8d, 0Eh
0x14000de99  mov     eax, r9d
0x14000de9c  or      eax, r8d
0x14000de9f  mov     r8d, eax
0x14000dea2  shr     r8d, 5
0x14000dea6  and     r8d, 1FFh
0x14000dead  lea     r9d, [r8+1]
0x14000deb1  cmp     r9d, 1FFh
0x14000deb8  ja      short loc_14000DEBF
0x14000deba  cmp     r9d, r8d
0x14000debd  jnb     short loc_14000DECA
0x14000debf  mov     r9d, ebx
0x14000dec2  mov     [r10+8], r11d
0x14000dec6  mov     [r10+4], r8d
0x14000deca  shl     r9d, 5
0x14000dece  xor     r9d, eax
0x14000ded1  and     r9d, 3FE0h
0x14000ded8  xor     r9d, eax
0x14000dedb  mov     eax, edx
0x14000dedd  lock cmpxchg [rsi], r9d
0x14000dee2  jz      short loc_14000DEEB
0x14000dee4  mov     edx, eax
0x14000dee6  jmp     loc_14000DE3D
0x14000deeb  not     edx
0x14000deed  and     edx, ebx
0x14000deef  mov     [r10], edx
0x14000def2  mov     dword ptr [r10+10h], 0
0x14000defa  mov     rax, r10
0x14000defd  pop     rdi
0x14000defe  pop     rsi
0x14000deff  pop     rbp
0x14000df00  pop     rbx
0x14000df01  retn
```
