# AudioSpecificConfig

- ea: `0x180036c60`
- end: `0x1800371a8`
- name: `AudioSpecificConfig`
- size: `1352`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800168e0`
- `0x180037490`

## callees

- `0x1800363f0`
- `0x180036c60`
- `0x1800371b0`
- `0x1800373b0`

## pseudocode

```c
__int64 __fastcall AudioSpecificConfig(int *a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // ebp
  bool v7; // cf
  int v8; // eax
  __int64 v9; // rax
  int v10; // r9d
  int v11; // eax
  __int64 v12; // rax
  bool v13; // zf
  unsigned int v14; // esi
  int AudioObjectType; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // eax

  v3 = 0;
  if ( a3 && *a3 && a1 )
    v3 = 8 * (a1[4] - a1[6]) - *a1;
  v7 = (unsigned int)*a1 < 5;
  a1[10] = -*a1 & 7;
  if ( v7 )
    FillBitCache(a1, 5u);
  *a1 -= 5;
  v8 = ((unsigned int)a1[1] >> *a1) & 0x1F;
  if ( v8 == 31 )
  {
    if ( (unsigned int)*a1 < 6 )
      FillBitCache(a1, 6u);
    *a1 -= 6;
    v8 = (((unsigned int)a1[1] >> *a1) & 0x3F) + 32;
  }
  *(_DWORD *)a2 = v8;
  if ( (unsigned int)*a1 < 4 )
    FillBitCache(a1, 4u);
  *a1 -= 4;
  v9 = ((unsigned int)a1[1] >> *a1) & 0xF;
  *(_DWORD *)(a2 + 4) = v9;
  if ( (_DWORD)v9 == 15 )
  {
    if ( (unsigned int)*a1 < 0x10 )
      FillBitCache(a1, 0x10u);
    *a1 -= 16;
    *(_DWORD *)(a2 + 8) = (unsigned __int16)((unsigned int)a1[1] >> *a1) << 8;
    if ( (unsigned int)*a1 < 8 )
      FillBitCache(a1, 8u);
    *a1 -= 8;
    *(_DWORD *)(a2 + 8) += (unsigned __int8)((unsigned int)a1[1] >> *a1);
  }
  else
  {
    *(_DWORD *)(a2 + 8) = dword_1800959A0[v9];
  }
  if ( (unsigned int)*a1 < 4 )
    FillBitCache(a1, 4u);
  *a1 -= 4;
  v10 = *(_DWORD *)a2;
  v11 = ((unsigned int)a1[1] >> *a1) & 0xF;
  *(_QWORD *)(a2 + 24) = -1;
  *(_DWORD *)(a2 + 32) = v11;
  if ( v10 == 5 || v10 == 29 )
  {
    *(_DWORD *)(a2 + 12) = 5;
    *(_DWORD *)(a2 + 24) = 1;
    if ( v10 == 29 )
      *(_DWORD *)(a2 + 28) = 1;
    if ( (unsigned int)*a1 < 4 )
      FillBitCache(a1, 4u);
    *a1 -= 4;
    v12 = ((unsigned int)a1[1] >> *a1) & 0xF;
    v13 = *(_DWORD *)(a2 + 4) == 15;
    *(_DWORD *)(a2 + 16) = v12;
    if ( v13 )
    {
      if ( (unsigned int)*a1 < 0x10 )
        FillBitCache(a1, 0x10u);
      *a1 -= 16;
      *(_DWORD *)(a2 + 20) = (unsigned __int16)((unsigned int)a1[1] >> *a1) << 8;
      if ( (unsigned int)*a1 < 8 )
        FillBitCache(a1, 8u);
      *a1 -= 8;
      *(_DWORD *)(a2 + 20) += (unsigned __int8)((unsigned int)a1[1] >> *a1);
    }
    else
    {
      *(_DWORD *)(a2 + 20) = dword_1800959A0[v12];
    }
    if ( (unsigned int)*a1 < 5 )
      FillBitCache(a1, 5u);
    *a1 -= 5;
    v10 = ((unsigned int)a1[1] >> *a1) & 0x1F;
    if ( v10 == 31 )
    {
      if ( (unsigned int)*a1 < 6 )
        FillBitCache(a1, 6u);
      *a1 -= 6;
      v10 = (((unsigned int)a1[1] >> *a1) & 0x3F) + 32;
    }
    *(_DWORD *)a2 = v10;
  }
  else
  {
    *(_DWORD *)(a2 + 12) = 0;
  }
  if ( v10 == 2 || v10 == 42 )
  {
    v14 = 0;
    switch ( v10 )
    {
      case 1:
      case 2:
      case 3:
      case 4:
      case 6:
      case 7:
      case 17:
      case 19:
      case 20:
      case 21:
      case 22:
      case 23:
        v14 = GASpecificConfig(a1, a2 + 52, *(unsigned int *)(a2 + 32));
        if ( !v14 )
        {
          if ( !*(_DWORD *)(a2 + 52) )
          {
            *(_DWORD *)(a2 + 36) = 1024;
            goto LABEL_50;
          }
          *(_DWORD *)(a2 + 36) = 960;
          v14 = -12;
        }
        break;
      case 42:
LABEL_50:
        switch ( *(_DWORD *)a2 )
        {
          case 0x11:
          case 0x13:
          case 0x14:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x18:
          case 0x19:
          case 0x1A:
          case 0x1B:
            goto LABEL_85;
          default:
            if ( a3 && *a3 && *(_DWORD *)(a2 + 12) != 5 && *a3 >= 8 * (a1[4] - a1[6]) + 16 - *a1 - v3 )
            {
              if ( (unsigned int)*a1 < 0xB )
                FillBitCache(a1, 0xBu);
              *a1 -= 11;
              if ( (((unsigned int)a1[1] >> *a1) & 0x7FF) == 0x2B7 )
              {
                AudioObjectType = GetAudioObjectType(a1);
                *(_DWORD *)(a2 + 12) = AudioObjectType;
                if ( AudioObjectType == 5 )
                {
                  if ( !*a1 )
                    FillBitCache(a1, 1u);
                  v13 = (((unsigned int)a1[1] >> --*a1) & 1) == 0;
                  *(_DWORD *)(a2 + 24) = ((unsigned int)a1[1] >> *a1) & 1;
                  if ( !v13 )
                  {
                    if ( (unsigned int)*a1 < 4 )
                      FillBitCache(a1, 4u);
                    *a1 -= 4;
                    v16 = ((unsigned int)a1[1] >> *a1) & 0xF;
                    v13 = *(_DWORD *)(a2 + 4) == 15;
                    *(_DWORD *)(a2 + 16) = v16;
                    if ( v13 )
                    {
                      if ( (unsigned int)*a1 < 0x10 )
                        FillBitCache(a1, 0x10u);
                      *a1 -= 16;
                      *(_DWORD *)(a2 + 20) = (unsigned __int16)((unsigned int)a1[1] >> *a1) << 8;
                      if ( (unsigned int)*a1 < 8 )
                        FillBitCache(a1, 8u);
                      *a1 -= 8;
                      *(_DWORD *)(a2 + 20) += (unsigned __int8)((unsigned int)a1[1] >> *a1);
                    }
                    else
                    {
                      *(_DWORD *)(a2 + 20) = dword_1800959A0[v16];
                    }
                    if ( *a3 >= 8 * (a1[4] - a1[6]) - *a1 - v3 + 12 )
                    {
                      if ( (unsigned int)*a1 < 0xB )
                        FillBitCache(a1, 0xBu);
                      *a1 -= 11;
                      if ( (((unsigned int)a1[1] >> *a1) & 0x7FF) == 0x548 )
                      {
                        if ( !*a1 )
                          FillBitCache(a1, 1u);
                        *(_DWORD *)(a2 + 28) = ((unsigned int)a1[1] >> --*a1) & 1;
                      }
                    }
                  }
                }
                else if ( *(_DWORD *)a2 == 2 && AudioObjectType == 2 )
                {
                  *(_DWORD *)(a2 + 12) = 0;
                }
              }
            }
            v17 = *(_DWORD *)(a2 + 12);
            if ( v17 > 0x1D || (v18 = 536870945, !_bittest(&v18, v17)) )
              v14 = -11;
            break;
        }
        break;
      default:
LABEL_85:
        v14 = -10;
        break;
    }
  }
  else
  {
    v14 = -10;
  }
  if ( !a3 )
    return v14;
  v19 = *a3;
  if ( !*a3 )
    return v14;
  v20 = 8 * (a1[4] - a1[6]) - *a1;
  *a3 = 0;
  if ( v20 > v3 )
  {
    v21 = v20 - v3;
    if ( v19 >= v21 )
    {
      *a3 = v19 - v21;
      return v14;
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180036c60  push    rbx
0x180036c62  push    rbp
0x180036c63  push    r15
0x180036c65  sub     rsp, 20h
0x180036c69  mov     [rsp+38h+arg_8], rdi
0x180036c6e  xor     ebp, ebp
0x180036c70  mov     [rsp+38h+arg_10], r12
0x180036c75  mov     r15, r8
0x180036c78  mov     rdi, rdx
0x180036c7b  mov     rbx, rcx
0x180036c7e  test    r8, r8
0x180036c81  jz      short loc_180036C98
0x180036c83  cmp     [r8], ebp
0x180036c86  jbe     short loc_180036C98
0x180036c88  test    rcx, rcx
0x180036c8b  jz      short loc_180036C98
0x180036c8d  mov     ebp, [rcx+10h]
0x180036c90  sub     ebp, [rcx+18h]
0x180036c93  shl     ebp, 3
0x180036c96  sub     ebp, [rcx]
0x180036c98  mov     eax, [rcx]
0x180036c9a  neg     eax
0x180036c9c  and     eax, 7
0x180036c9f  cmp     dword ptr [rcx], 5
0x180036ca2  mov     [rcx+28h], eax
0x180036ca5  jnb     short loc_180036CB1
0x180036ca7  mov     edx, 5
0x180036cac  call    FillBitCache
0x180036cb1  add     dword ptr [rbx], 0FFFFFFFBh
0x180036cb4  mov     eax, [rbx+4]
0x180036cb7  mov     ecx, [rbx]
0x180036cb9  shr     eax, cl
0x180036cbb  and     eax, 1Fh
0x180036cbe  cmp     eax, 1Fh
0x180036cc1  jnz     short loc_180036CE5
0x180036cc3  cmp     ecx, 6
0x180036cc6  jnb     short loc_180036CD5
0x180036cc8  mov     edx, 6
0x180036ccd  mov     rcx, rbx
0x180036cd0  call    FillBitCache
0x180036cd5  add     dword ptr [rbx], 0FFFFFFFAh
0x180036cd8  mov     eax, [rbx+4]
0x180036cdb  mov     ecx, [rbx]
0x180036cdd  shr     eax, cl
0x180036cdf  and     eax, 3Fh
0x180036ce2  add     eax, 20h ; ' '
0x180036ce5  mov     [rdi], eax
0x180036ce7  cmp     dword ptr [rbx], 4
0x180036cea  jnb     short loc_180036CF9
0x180036cec  mov     edx, 4
0x180036cf1  mov     rcx, rbx
0x180036cf4  call    FillBitCache
0x180036cf9  add     dword ptr [rbx], 0FFFFFFFCh
0x180036cfc  lea     r12, __ImageBase
0x180036d03  mov     eax, [rbx+4]
0x180036d06  mov     ecx, [rbx]
0x180036d08  shr     eax, cl
0x180036d0a  and     eax, 0Fh
0x180036d0d  mov     [rdi+4], eax
0x180036d10  cmp     eax, 0Fh
0x180036d13  jnz     short loc_180036D5E
0x180036d15  cmp     dword ptr [rbx], 10h
0x180036d18  jnb     short loc_180036D27
0x180036d1a  mov     edx, 10h
0x180036d1f  mov     rcx, rbx
0x180036d22  call    FillBitCache
0x180036d27  add     dword ptr [rbx], 0FFFFFFF0h
0x180036d2a  mov     eax, [rbx+4]
0x180036d2d  mov     ecx, [rbx]
0x180036d2f  shr     eax, cl
0x180036d31  movzx   eax, ax
0x180036d34  shl     eax, 8
0x180036d37  mov     [rdi+8], eax
0x180036d3a  cmp     dword ptr [rbx], 8
0x180036d3d  jnb     short loc_180036D4C
0x180036d3f  mov     edx, 8
0x180036d44  mov     rcx, rbx
0x180036d47  call    FillBitCache
0x180036d4c  add     dword ptr [rbx], 0FFFFFFF8h
0x180036d4f  mov     eax, [rbx+4]
0x180036d52  mov     ecx, [rbx]
0x180036d54  shr     eax, cl
0x180036d56  movzx   eax, al
0x180036d59  add     [rdi+8], eax
0x180036d5c  jmp     short loc_180036D69
0x180036d5e  mov     eax, ds:rva dword_1800959A0[r12+rax*4]
0x180036d66  mov     [rdi+8], eax
0x180036d69  cmp     dword ptr [rbx], 4
0x180036d6c  jnb     short loc_180036D7B
0x180036d6e  mov     edx, 4
0x180036d73  mov     rcx, rbx
0x180036d76  call    FillBitCache
0x180036d7b  add     dword ptr [rbx], 0FFFFFFFCh
0x180036d7e  mov     eax, [rbx+4]
0x180036d81  mov     ecx, [rbx]
0x180036d83  mov     r9d, [rdi]
0x180036d86  shr     eax, cl
0x180036d88  and     eax, 0Fh
0x180036d8b  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180036d93  mov     [rdi+20h], eax
0x180036d96  cmp     r9d, 5
0x180036d9a  jz      short loc_180036DAE
0x180036d9c  cmp     r9d, 1Dh
0x180036da0  jz      short loc_180036DAE
0x180036da2  mov     dword ptr [rdi+0Ch], 0
0x180036da9  jmp     loc_180036E96
0x180036dae  mov     dword ptr [rdi+0Ch], 5
0x180036db5  mov     dword ptr [rdi+18h], 1
0x180036dbc  cmp     r9d, 1Dh
0x180036dc0  jnz     short loc_180036DC9
0x180036dc2  mov     dword ptr [rdi+1Ch], 1
0x180036dc9  cmp     dword ptr [rbx], 4
0x180036dcc  jnb     short loc_180036DDB
0x180036dce  mov     edx, 4
0x180036dd3  mov     rcx, rbx
0x180036dd6  call    FillBitCache
0x180036ddb  add     dword ptr [rbx], 0FFFFFFFCh
0x180036dde  mov     eax, [rbx+4]
0x180036de1  mov     ecx, [rbx]
0x180036de3  shr     eax, cl
0x180036de5  and     eax, 0Fh
0x180036de8  cmp     dword ptr [rdi+4], 0Fh
0x180036dec  mov     [rdi+10h], eax
0x180036def  jnz     short loc_180036E3A
0x180036df1  cmp     dword ptr [rbx], 10h
0x180036df4  jnb     short loc_180036E03
0x180036df6  mov     edx, 10h
0x180036dfb  mov     rcx, rbx
0x180036dfe  call    FillBitCache
0x180036e03  add     dword ptr [rbx], 0FFFFFFF0h
0x180036e06  mov     eax, [rbx+4]
0x180036e09  mov     ecx, [rbx]
0x180036e0b  shr     eax, cl
0x180036e0d  movzx   eax, ax
0x180036e10  shl     eax, 8
0x180036e13  mov     [rdi+14h], eax
0x180036e16  cmp     dword ptr [rbx], 8
0x180036e19  jnb     short loc_180036E28
0x180036e1b  mov     edx, 8
0x180036e20  mov     rcx, rbx
0x180036e23  call    FillBitCache
0x180036e28  add     dword ptr [rbx], 0FFFFFFF8h
0x180036e2b  mov     eax, [rbx+4]
0x180036e2e  mov     ecx, [rbx]
0x180036e30  shr     eax, cl
0x180036e32  movzx   eax, al
0x180036e35  add     [rdi+14h], eax
0x180036e38  jmp     short loc_180036E45
0x180036e3a  mov     eax, ds:rva dword_1800959A0[r12+rax*4]
0x180036e42  mov     [rdi+14h], eax
0x180036e45  cmp     dword ptr [rbx], 5
0x180036e48  jnb     short loc_180036E57
0x180036e4a  mov     edx, 5
0x180036e4f  mov     rcx, rbx
0x180036e52  call    FillBitCache
0x180036e57  add     dword ptr [rbx], 0FFFFFFFBh
0x180036e5a  mov     r9d, [rbx+4]
0x180036e5e  mov     ecx, [rbx]
0x180036e60  shr     r9d, cl
0x180036e63  and     r9d, 1Fh
0x180036e67  cmp     r9d, 1Fh
0x180036e6b  jnz     short loc_180036E93
0x180036e6d  cmp     ecx, 6
0x180036e70  jnb     short loc_180036E7F
0x180036e72  mov     edx, 6
0x180036e77  mov     rcx, rbx
0x180036e7a  call    FillBitCache
0x180036e7f  add     dword ptr [rbx], 0FFFFFFFAh
0x180036e82  mov     r9d, [rbx+4]
0x180036e86  mov     ecx, [rbx]
0x180036e88  shr     r9d, cl
0x180036e8b  and     r9d, 3Fh
0x180036e8f  add     r9d, 20h ; ' '
0x180036e93  mov     [rdi], r9d
0x180036e96  mov     [rsp+38h+arg_0], rsi
0x180036e9b  cmp     r9d, 2
0x180036e9f  jz      short loc_180036EB1
0x180036ea1  cmp     r9d, 2Ah ; '*'
0x180036ea5  jz      short loc_180036EB1
0x180036ea7  mov     esi, 0FFFFFFF6h
0x180036eac  jmp     loc_1800370E7
0x180036eb1  lea     eax, [r9-1]; switch 42 cases
0x180036eb5  mov     [rsp+38h+arg_18], r14
0x180036eba  cmp     eax, 29h
0x180036ebd  ja      def_180036EDB; jumptable 0000000180036EDB default case, cases 5,8-16,18,24-41
0x180036ec3  cdqe
0x180036ec5  xor     esi, esi
0x180036ec7  movzx   eax, ds:(byte_180037150 - 180000000h)[r12+rax]
0x180036ed0  mov     ecx, ds:(jpt_180036EDB - 180000000h)[r12+rax*4]
0x180036ed8  add     rcx, r12
0x180036edb  jmp     rcx; switch jump
0x180036ee1  mov     r8d, [rdi+20h]; jumptable 0000000180036EDB cases 1-4,6,7,17,19-23
0x180036ee5  lea     rdx, [rdi+34h]
0x180036ee9  mov     rcx, rbx
0x180036eec  call    GASpecificConfig
0x180036ef1  mov     esi, eax
0x180036ef3  test    eax, eax
0x180036ef5  jnz     loc_1800370E2
0x180036efb  cmp     [rdi+34h], eax
0x180036efe  jnz     short loc_180036F24
0x180036f00  mov     dword ptr [rdi+24h], 400h
0x180036f07  mov     eax, [rdi]; jumptable 0000000180036EDB case 42
0x180036f09  add     eax, 0FFFFFFEFh; switch 11 cases
0x180036f0c  cmp     eax, 0Ah
0x180036f0f  ja      short def_180036F1E; jumptable 0000000180036F1E default case, case 18
0x180036f11  cdqe
0x180036f13  mov     ecx, ds:(jpt_180036F1E - 180000000h)[r12+rax*4]
0x180036f1b  add     rcx, r12
0x180036f1e  jmp     rcx; switch jump
0x180036f24  mov     dword ptr [rdi+24h], 3C0h
0x180036f2b  mov     esi, 0FFFFFFF4h
0x180036f30  jmp     loc_1800370E2
0x180036f35  test    r15, r15; jumptable 0000000180036F1E default case, case 18
0x180036f38  jz      loc_1800370C4
0x180036f3e  mov     ecx, [r15]
0x180036f41  test    ecx, ecx
0x180036f43  jz      loc_1800370C4
0x180036f49  cmp     dword ptr [rdi+0Ch], 5
0x180036f4d  jz      loc_1800370C4
0x180036f53  mov     eax, [rbx+10h]
0x180036f56  sub     eax, [rbx+18h]
0x180036f59  mov     edx, [rbx]
0x180036f5b  lea     eax, ds:10h[rax*8]
0x180036f62  sub     eax, edx
0x180036f64  sub     eax, ebp
0x180036f66  cmp     ecx, eax
0x180036f68  jb      loc_1800370C4
0x180036f6e  cmp     edx, 0Bh
0x180036f71  jnb     short loc_180036F80
0x180036f73  mov     edx, 0Bh
0x180036f78  mov     rcx, rbx
0x180036f7b  call    FillBitCache
0x180036f80  add     dword ptr [rbx], 0FFFFFFF5h
0x180036f83  mov     eax, [rbx+4]
0x180036f86  mov     ecx, [rbx]
0x180036f88  shr     eax, cl
0x180036f8a  and     eax, 7FFh
0x180036f8f  cmp     eax, 2B7h
0x180036f94  jnz     loc_1800370C4
0x180036f9a  mov     rcx, rbx
0x180036f9d  call    GetAudioObjectType
0x180036fa2  mov     [rdi+0Ch], eax
0x180036fa5  cmp     eax, 5
0x180036fa8  jnz     loc_1800370B3
0x180036fae  cmp     dword ptr [rbx], 1
0x180036fb1  jnb     short loc_180036FC0
0x180036fb3  mov     edx, 1
0x180036fb8  mov     rcx, rbx
0x180036fbb  call    FillBitCache
0x180036fc0  dec     dword ptr [rbx]
0x180036fc2  mov     eax, [rbx+4]
0x180036fc5  mov     ecx, [rbx]
0x180036fc7  shr     eax, cl
0x180036fc9  and     eax, 1
0x180036fcc  mov     [rdi+18h], eax
0x180036fcf  jz      loc_1800370C4
0x180036fd5  cmp     dword ptr [rbx], 4
0x180036fd8  jnb     short loc_180036FE7
0x180036fda  mov     edx, 4
0x180036fdf  mov     rcx, rbx
0x180036fe2  call    FillBitCache
0x180036fe7  add     dword ptr [rbx], 0FFFFFFFCh
0x180036fea  mov     eax, [rbx+4]
0x180036fed  mov     ecx, [rbx]
0x180036fef  shr     eax, cl
0x180036ff1  and     eax, 0Fh
0x180036ff4  cmp     dword ptr [rdi+4], 0Fh
0x180036ff8  mov     [rdi+10h], eax
0x180036ffb  jnz     short loc_180037046
0x180036ffd  cmp     dword ptr [rbx], 10h
0x180037000  jnb     short loc_18003700F
0x180037002  mov     edx, 10h
0x180037007  mov     rcx, rbx
0x18003700a  call    FillBitCache
0x18003700f  add     dword ptr [rbx], 0FFFFFFF0h
0x180037012  mov     eax, [rbx+4]
0x180037015  mov     ecx, [rbx]
0x180037017  shr     eax, cl
0x180037019  movzx   eax, ax
0x18003701c  shl     eax, 8
0x18003701f  mov     [rdi+14h], eax
0x180037022  cmp     dword ptr [rbx], 8
0x180037025  jnb     short loc_180037034
0x180037027  mov     edx, 8
0x18003702c  mov     rcx, rbx
0x18003702f  call    FillBitCache
0x180037034  add     dword ptr [rbx], 0FFFFFFF8h
0x180037037  mov     eax, [rbx+4]
0x18003703a  mov     ecx, [rbx]
0x18003703c  shr     eax, cl
0x18003703e  movzx   eax, al
0x180037041  add     [rdi+14h], eax
0x180037044  jmp     short loc_180037051
0x180037046  mov     eax, ds:rva dword_1800959A0[r12+rax*4]
0x18003704e  mov     [rdi+14h], eax
0x180037051  mov     eax, [rbx+10h]
0x180037054  sub     eax, [rbx+18h]
0x180037057  mov     ecx, [rbx]
0x180037059  shl     eax, 3
0x18003705c  sub     eax, ecx
  ... truncated ...
```
