# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180030e70`
- end: `0x18003114a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002db04`

## callees

- `0x180030e70`

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
0x180030e70  push    rbx
0x180030e72  push    rbp
0x180030e73  push    rsi
0x180030e74  push    rdi
0x180030e75  xor     eax, eax
0x180030e77  xorps   xmm0, xmm0
0x180030e7a  mov     r11d, r8d
0x180030e7d  mov     rsi, rdx
0x180030e80  mov     r10, rcx
0x180030e83  mov     r9d, r8d
0x180030e86  movups  xmmword ptr [rcx], xmm0
0x180030e89  mov     [rcx+10h], rax
0x180030e8d  test    r8d, r8d
0x180030e90  jz      loc_180031074
0x180030e96  sub     r9d, 1
0x180030e9a  jz      loc_180030FBB
0x180030ea0  sub     r9d, 1
0x180030ea4  jz      loc_180030F42
0x180030eaa  sub     r9d, 1
0x180030eae  jz      loc_180030F42
0x180030eb4  sub     r9d, 1
0x180030eb8  jz      loc_180031074
0x180030ebe  sub     r9d, 1
0x180030ec2  jz      loc_180030FBB
0x180030ec8  sub     r9d, 1
0x180030ecc  jz      short loc_180030F42
0x180030ece  cmp     r9d, 1
0x180030ed2  jz      short loc_180030F42
0x180030ed4  add     r8d, 0FFFFFEC0h
0x180030edb  lea     ebx, [rax+1]
0x180030ede  cmp     r8d, 40h ; '@'
0x180030ee2  jge     short loc_180030F2D
0x180030ee4  mov     eax, [rdx+4]
0x180030ee7  lea     ecx, [rbx+0Fh]
0x180030eea  mov     r9d, r8d
0x180030eed  shl     r9d, 5
0x180030ef1  test    cl, al
0x180030ef3  jz      short loc_180030F06
0x180030ef5  mov     edx, eax
0x180030ef7  shr     edx, 5
0x180030efa  and     edx, 3Fh
0x180030efd  cmp     edx, r8d
0x180030f00  jnz     short loc_180030F06
0x180030f02  mov     edx, ebx
0x180030f04  jmp     short loc_180030F08
0x180030f06  xor     edx, edx
0x180030f08  mov     [r10+10h], edx
0x180030f0c  mov     edx, r9d
0x180030f0f  xor     edx, eax
0x180030f11  and     edx, 7E0h
0x180030f17  xor     edx, eax
0x180030f19  or      edx, ecx
0x180030f1b  lock cmpxchg [rsi+4], edx
0x180030f20  jnz     short loc_180030EF1
0x180030f22  cmp     dword ptr [r10+10h], 0
0x180030f27  jnz     loc_180031142
0x180030f2d  mov     [r10+8], r11d
0x180030f31  mov     [r10+4], ebx
0x180030f35  mov     dword ptr [r10+0Ch], 0
0x180030f3d  jmp     loc_180031142
0x180030f42  xor     ecx, ecx
0x180030f44  sub     r11d, 2
0x180030f48  jz      short loc_180030F70
0x180030f4a  sub     r11d, 1
0x180030f4e  jz      short loc_180030F69
0x180030f50  sub     r11d, 3
0x180030f54  jz      short loc_180030F62
0x180030f56  cmp     r11d, 1
0x180030f5a  jnz     short loc_180030F75
0x180030f5c  lea     ecx, [r11+0Fh]
0x180030f60  jmp     short loc_180030F75
0x180030f62  mov     ecx, 4
0x180030f67  jmp     short loc_180030F75
0x180030f69  mov     ecx, 8
0x180030f6e  jmp     short loc_180030F75
0x180030f70  mov     ecx, 2
0x180030f75  mov     edx, [rdx]
0x180030f77  mov     ebx, 1
0x180030f7c  xor     eax, eax
0x180030f7e  mov     r8d, ecx
0x180030f81  or      r8d, edx
0x180030f84  cmp     r8d, edx
0x180030f87  mov     r9d, r8d
0x180030f8a  setz    al
0x180030f8d  or      r9d, ebx
0x180030f90  cmp     r8d, edx
0x180030f93  mov     [r10+10h], eax
0x180030f97  mov     eax, edx
0x180030f99  cmovz   r9d, r8d
0x180030f9d  lock cmpxchg [rsi], r9d
0x180030fa2  jz      short loc_180030FA8
0x180030fa4  mov     edx, eax
0x180030fa6  jmp     short loc_180030F7C
0x180030fa8  test    bl, r9b
0x180030fab  jz      short loc_180030FB1
0x180030fad  test    bl, dl
0x180030faf  jz      short loc_180030FB3
0x180030fb1  xor     ebx, ebx
0x180030fb3  mov     [r10], ebx
0x180030fb6  jmp     loc_180031142
0x180030fbb  mov     ecx, [rdx]
0x180030fbd  xor     r9d, r9d
0x180030fc0  cmp     r11d, 5
0x180030fc4  mov     ebx, 1
0x180030fc9  setz    r9b
0x180030fcd  mov     eax, ecx
0x180030fcf  mov     dword ptr [r10+4], 0
0x180030fd7  or      eax, ebx
0x180030fd9  mov     edx, eax
0x180030fdb  shr     edx, 16h
0x180030fde  and     edx, ebx
0x180030fe0  cmp     edx, r9d
0x180030fe3  jz      short loc_180031025
0x180030fe5  mov     r8d, eax
0x180030fe8  shr     r8d, 0Fh
0x180030fec  and     r8d, 7Fh
0x180030ff0  jbe     short loc_18003100A
0x180030ff2  cmp     r11d, ebx
0x180030ff5  mov     [r10+4], r8d
0x180030ff9  mov     edx, 5
0x180030ffe  cmovnz  edx, ebx
0x180031001  and     eax, 0FFC07FFFh
0x180031006  mov     [r10+8], edx
0x18003100a  xor     r8d, r8d
0x18003100d  mov     edx, 400000h
0x180031012  cmp     r11d, 5
0x180031016  cmovz   r8d, edx
0x18003101a  mov     edx, eax
0x18003101c  btr     edx, 16h
0x180031020  mov     eax, r8d
0x180031023  or      eax, edx
0x180031025  mov     edx, eax
0x180031027  shr     edx, 0Fh
0x18003102a  and     edx, 7Fh
0x18003102d  lea     r8d, [rdx+1]
0x180031031  cmp     r8d, 7Fh
0x180031035  ja      short loc_18003103C
0x180031037  cmp     r8d, edx
0x18003103a  jnb     short loc_180031047
0x18003103c  mov     r8d, ebx
0x18003103f  mov     [r10+8], r11d
0x180031043  mov     [r10+4], edx
0x180031047  shl     r8d, 0Fh
0x18003104b  xor     r8d, eax
0x18003104e  and     r8d, 3F8000h
0x180031055  xor     r8d, eax
0x180031058  mov     eax, ecx
0x18003105a  lock cmpxchg [rsi], r8d
0x18003105f  jz      short loc_180031068
0x180031061  mov     ecx, eax
0x180031063  jmp     loc_180030FCD
0x180031068  not     ecx
0x18003106a  and     ecx, ebx
0x18003106c  mov     [r10], ecx
0x18003106f  jmp     loc_18003113A
0x180031074  mov     edx, [rdx]
0x180031076  xor     ebp, ebp
0x180031078  lea     ecx, [rbp+4]
0x18003107b  cmp     r11d, ecx
0x18003107e  lea     ebx, [rcx-3]
0x180031081  setz    bpl
0x180031085  mov     eax, edx
0x180031087  mov     dword ptr [r10+4], 0
0x18003108f  or      eax, ebx
0x180031091  mov     r8d, eax
0x180031094  shr     r8d, 0Eh
0x180031098  and     r8d, ebx
0x18003109b  cmp     r8d, ebp
0x18003109e  jz      short loc_1800310E7
0x1800310a0  mov     edi, eax
0x1800310a2  shr     edi, 5
0x1800310a5  and     edi, 1FFh
0x1800310ab  jbe     short loc_1800310C9
0x1800310ad  mov     r8d, r11d
0x1800310b0  mov     [r10+4], edi
0x1800310b4  neg     r8d
0x1800310b7  sbb     r9d, r9d
0x1800310ba  not     r9d
0x1800310bd  and     r9d, ecx
0x1800310c0  mov     [r10+8], r9d
0x1800310c4  and     eax, 0FFFFC01Fh
0x1800310c9  xor     r9d, r9d
0x1800310cc  mov     r8d, 4000h
0x1800310d2  cmp     r11d, ecx
0x1800310d5  cmovz   r9d, r8d
0x1800310d9  mov     r8d, eax
0x1800310dc  btr     r8d, 0Eh
0x1800310e1  mov     eax, r9d
0x1800310e4  or      eax, r8d
0x1800310e7  mov     r8d, eax
0x1800310ea  shr     r8d, 5
0x1800310ee  and     r8d, 1FFh
0x1800310f5  lea     r9d, [r8+1]
0x1800310f9  cmp     r9d, 1FFh
0x180031100  ja      short loc_180031107
0x180031102  cmp     r9d, r8d
0x180031105  jnb     short loc_180031112
0x180031107  mov     r9d, ebx
0x18003110a  mov     [r10+8], r11d
0x18003110e  mov     [r10+4], r8d
0x180031112  shl     r9d, 5
0x180031116  xor     r9d, eax
0x180031119  and     r9d, 3FE0h
0x180031120  xor     r9d, eax
0x180031123  mov     eax, edx
0x180031125  lock cmpxchg [rsi], r9d
0x18003112a  jz      short loc_180031133
0x18003112c  mov     edx, eax
0x18003112e  jmp     loc_180031085
0x180031133  not     edx
0x180031135  and     edx, ebx
0x180031137  mov     [r10], edx
0x18003113a  mov     dword ptr [r10+10h], 0
0x180031142  mov     rax, r10
0x180031145  pop     rdi
0x180031146  pop     rsi
0x180031147  pop     rbp
0x180031148  pop     rbx
0x180031149  retn
```
