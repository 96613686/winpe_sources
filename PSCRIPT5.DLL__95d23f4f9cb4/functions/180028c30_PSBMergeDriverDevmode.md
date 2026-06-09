# PSBMergeDriverDevmode

- ea: `0x180028c30`
- end: `0x180029341`
- name: `PSBMergeDriverDevmode`
- size: `1809`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180030a2c`

## callees

- `0x180028c30`
- `0x18002dd70`
- `0x18002f6f8`
- `0x18002fac0`
- `0x1800330fc`
- `0x180034afc`
- `0x180053aa0`
- `0x18005403c`
- `0x18005bf74`

## string_xrefs

- `0x180029270`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall PSBMergeDriverDevmode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _WORD *a8)
{
  __int64 v8; // rdi
  __int64 v9; // r11
  _DWORD *v11; // r15
  _OWORD *v14; // r13
  char *v15; // rbp
  int v16; // r10d
  int v17; // ecx
  __int16 v18; // r14
  __int64 KeywordMatchFeature; // rax
  __int64 v20; // r9
  unsigned int v21; // ecx
  __int16 v22; // ax
  int v23; // edx
  __int64 v24; // rax
  int v25; // edx
  unsigned int v26; // eax
  __int64 v27; // rbp
  __int64 v28; // rax
  _DWORD *v29; // rbp
  __int16 v30; // r8
  __int16 v31; // r10
  __int64 v32; // rcx
  unsigned int v33; // eax
  __int64 v34; // rdx
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rdx
  unsigned int v40; // ecx
  __int64 v41; // rax
  _OWORD *v42; // rcx
  __int128 v43; // xmm1
  __int64 v44; // rbp
  __int64 v45; // rdx
  unsigned __int16 v46; // cx
  unsigned __int16 v47; // r8
  int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // ecx
  __int64 v51; // rdx
  __int64 v52; // rdx
  char v54; // [rsp+A8h] [rbp+10h] BYREF

  v8 = a7;
  v9 = 0;
  v11 = (_DWORD *)(a1 + *(unsigned __int16 *)(a1 + 68));
  v14 = (_OWORD *)(a7 + *(unsigned __int16 *)(a7 + 68));
  if ( a4[15] )
    v15 = (char *)a4 + (unsigned int)a4[15];
  else
    v15 = 0;
  v16 = 1;
  if ( !*(_DWORD *)(a3 + 300) && (*(_BYTE *)(a7 + 72) & 0x40) != 0 )
  {
    v17 = *(_DWORD *)(a7 + 180);
    if ( (unsigned int)(v17 - 1) <= 1 )
    {
      *(_DWORD *)(a1 + 72) |= 0x40u;
      *(_DWORD *)(a1 + 180) = v17;
    }
  }
  if ( (*(_DWORD *)(v8 + 72) & 0x200) != 0
    && ((unsigned __int16)(*(_WORD *)(v8 + 88) - 1) <= 0xEu || *(__int16 *)(v8 + 88) >= 256) )
  {
    *(_DWORD *)(a1 + 72) |= 0x200u;
    *(_WORD *)(a1 + 88) = *(_WORD *)(v8 + 88);
  }
  if ( (*(_BYTE *)(v8 + 72) & 1) != 0 )
  {
    v18 = *(_WORD *)(v8 + 76);
    if ( (unsigned __int16)(v18 - 1) <= 1u )
    {
      if ( !*(_DWORD *)(a3 + 300)
        || (KeywordMatchFeature = PInternalGetKeywordMatchFeature(a3, "PageOrientation", 1, &v54),
            v9 = 0,
            v16 = 1,
            KeywordMatchFeature) )
      {
        *(_DWORD *)(a1 + 72) |= 1u;
        *(_WORD *)(a1 + 76) = v18;
      }
    }
  }
  if ( (*(_BYTE *)(v8 + 72) & 0xC) == 0xC && *(__int16 *)(v8 + 82) > 0 && *(__int16 *)(v8 + 80) > 0 )
  {
    v20 = 256;
    v21 = *(_DWORD *)(a1 + 72) & 0xFFFEFFF1 | 0xC;
    *(_DWORD *)(a1 + 72) = v21;
    *(_WORD *)(a1 + 82) = *(_WORD *)(v8 + 82);
    *(_WORD *)(a1 + 80) = *(_WORD *)(v8 + 80);
    if ( (*(_BYTE *)(v8 + 72) & 2) != 0 && *(_WORD *)(v8 + 78) == 256 )
    {
      *(_DWORD *)(a1 + 72) = v21 | 2;
      *(_WORD *)(a1 + 78) = *(_WORD *)(v8 + 78);
    }
  }
  else
  {
    if ( (*(_BYTE *)(v8 + 72) & 2) != 0 )
    {
      if ( *(_WORD *)(v8 + 78) != 0x7FFF
        || (*(_BYTE *)(a3 + 140) & 0x20) != 0 && (*(_DWORD *)(a3 + 16) >= 0x40003u || (v15[44] & 2) != 0) )
      {
        *(_DWORD *)(a1 + 72) = *(_DWORD *)(a1 + 72) & 0xFFFEFFF1 | 2;
        *(_WORD *)(a1 + 78) = *(_WORD *)(v8 + 78);
      }
    }
    else if ( (*(_DWORD *)(v8 + 72) & 0x10000) != 0 )
    {
      *(_DWORD *)(a1 + 72) = *(_DWORD *)(a1 + 72) & 0xFFFEFFF1 | 0x10000;
      CopyStringW(a1 + 102, v8 + 102);
    }
    v20 = 256;
  }
  if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9
    && (*(_BYTE *)(v8 + 72) & 0x10) != 0
    && (unsigned __int16)(*(_WORD *)(v8 + 84) - v16) <= 0x3E7u )
  {
    *(_DWORD *)(a1 + 72) |= 0x10u;
    *(_WORD *)(a1 + 84) = *(_WORD *)(v8 + 84);
  }
  if ( (*(_DWORD *)(v8 + 72) & 0x100) != 0 )
  {
    v22 = *(_WORD *)(v8 + 86);
    if ( v22 >= (__int16)v16 && v22 <= *(__int16 *)(a3 + 60) )
    {
      *(_DWORD *)(a1 + 72) |= 0x100u;
      *(_WORD *)(a1 + 86) = *(_WORD *)(v8 + 86);
    }
  }
  v23 = *(_DWORD *)(v8 + 72);
  if ( (v23 & 0x1000) != 0 )
  {
    v24 = *(unsigned int *)(a3 + 216);
    if ( (_DWORD)v24 )
    {
      if ( v24 + *(_QWORD *)(a3 + 328) && (unsigned __int16)(*(_WORD *)(v8 + 94) - v16) <= 2u )
      {
        *(_DWORD *)(a1 + 72) |= 0x1000u;
        *(_WORD *)(a1 + 94) = *(_WORD *)(v8 + 94);
        v23 = *(_DWORD *)(v8 + 72);
      }
    }
  }
  if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9 && (v23 & 0x8000) != 0 && *(_WORD *)(v8 + 100) <= (unsigned __int16)v16 )
  {
    *(_DWORD *)(a1 + 72) |= 0x8000u;
    *(_WORD *)(a1 + 100) = *(_WORD *)(v8 + 100);
    v23 = *(_DWORD *)(v8 + 72);
  }
  if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9 && (v23 & 0x4000) != 0 && (unsigned __int16)(*(_WORD *)(v8 + 98) - v16) <= 2u )
  {
    *(_DWORD *)(a1 + 72) |= 0x4000u;
    *(_WORD *)(a1 + 98) = 3 - (*(_WORD *)(v8 + 98) != 3);
    v23 = *(_DWORD *)(v8 + 72);
  }
  if ( (*(_BYTE *)(a3 + 140) & 8) != 0 )
  {
    if ( (v23 & 0x800) != 0 && (unsigned __int16)(*(_WORD *)(v8 + 92) - v16) <= (unsigned __int16)v16 )
    {
      *(_DWORD *)(a1 + 72) |= 0x800u;
      *(_WORD *)(a1 + 92) = *(_WORD *)(v8 + 92);
      v23 = *(_DWORD *)(v8 + 72);
    }
    if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9 )
    {
      if ( (v23 & 0x800000) != 0 && (unsigned int)(*(_DWORD *)(v8 + 188) - v16) <= 3 )
      {
        *(_DWORD *)(a1 + 72) |= 0x800000u;
        *(_DWORD *)(a1 + 188) = *(_DWORD *)(v8 + 188);
        v23 = *(_DWORD *)(v8 + 72);
      }
      if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9
        && (v23 & 0x1000000) != 0
        && (unsigned int)(*(_DWORD *)(v8 + 192) - v16) <= 3 )
      {
        *(_DWORD *)(a1 + 72) |= 0x1000000u;
        *(_DWORD *)(a1 + 192) = *(_DWORD *)(v8 + 192);
      }
    }
  }
  v25 = *(_DWORD *)(v8 + 72) & 0x2400;
  if ( v25 )
  {
    v26 = *(_DWORD *)(a3 + 204);
    if ( v26 )
    {
      v27 = v26;
      v28 = *(_QWORD *)(a3 + 328);
      v29 = (_DWORD *)(v28 + v27);
      if ( v29 )
      {
        if ( v25 == 1024 )
        {
          v30 = *(_WORD *)(v8 + 90);
        }
        else
        {
          v30 = *(_WORD *)(v8 + 96);
          if ( v25 != 0x2000 )
          {
            v31 = *(_WORD *)(v8 + 90);
            goto LABEL_73;
          }
        }
        v31 = v30;
LABEL_73:
        if ( *(_DWORD *)(v28 + 56) == (_DWORD)v9 )
          v32 = v9;
        else
          v32 = v28 + *(unsigned int *)(v28 + 56);
        v33 = *(_DWORD *)(v32 + 204);
        if ( v33 && (v34 = *(_QWORD *)(v32 + 328) + v33) != 0 )
        {
          v35 = DwInternalMapToOptIndex(v32, v34, v31, v30, v9);
          LODWORD(v9) = 0;
          v20 = 256;
        }
        else
        {
          v35 = 255;
        }
        if ( v35 < v29[13] )
        {
          v36 = *(_QWORD *)(a3 + 328) + v29[14] + v29[12] * v35;
          if ( v36 )
          {
            *(_DWORD *)(a1 + 72) |= 0x2400u;
            *(_WORD *)(a1 + 90) = *(_WORD *)(v36 + 56);
            *(_WORD *)(a1 + 96) = *(_WORD *)(v36 + 60);
          }
        }
      }
    }
  }
  v37 = 0x2000000;
  if ( (*(_DWORD *)(v8 + 72) & 0x2000000) != 0 )
  {
    v38 = *(unsigned int *)(a3 + 224);
    if ( (_DWORD)v38 )
    {
      v39 = v38 + *(_QWORD *)(a3 + 328);
      if ( v39 )
      {
        v40 = *(_DWORD *)(v8 + 196);
        if ( v40 - 1 <= 2 || v40 >= 0x100 && v40 < *(_DWORD *)(v39 + 52) + 256 )
        {
          *(_DWORD *)(a1 + 72) |= 0x2000000u;
          *(_DWORD *)(a1 + 196) = *(_DWORD *)(v8 + 196);
        }
      }
    }
  }
  if ( *(_DWORD *)(a3 + 300) != (_DWORD)v9 )
    VMergeXPSDevmode(a3, v8, a1, 256);
  if ( *(_DWORD *)v14 == 1447645776 )
  {
    v41 = 5;
    v42 = v11;
    do
    {
      *v42 = *v14;
      v42[1] = v14[1];
      v42[2] = v14[2];
      v42[3] = v14[3];
      v42[4] = v14[4];
      v42[5] = v14[5];
      v42[6] = v14[6];
      v43 = v14[7];
      v14 += 8;
      v42[7] = v43;
      v42 += 8;
      --v41;
    }
    while ( v41 );
    v44 = a5;
    *v42 = *v14;
    v42[1] = v14[1];
    v42[2] = v14[2];
    v42[3] = v14[3];
    v42[4] = v14[4];
    v42[5] = v14[5];
    v42[6] = v14[6];
    *((_DWORD *)v42 + 28) = *((_DWORD *)v14 + 28);
    if ( v11[47] != a4[3] )
    {
      InitDefaultOptions(a4, v11 + 49, v37, 0);
      v11[48] = a4[5];
      v11[47] = a4[3];
      if ( a8[33] >= 0x600u && a8[35] > 0x2C4u )
      {
        v45 = (unsigned __int16)a8[34];
        if ( *(_DWORD *)((char *)a8 + v45) == 1447645776 )
        {
          v46 = *(_WORD *)((char *)a8 + v45 + 114);
          if ( v46 > 0x2C4u )
          {
            v47 = *(_WORD *)((char *)a8 + v45 + 112);
            if ( v47 )
            {
              if ( v46 > v47 && a8[35] >= v46 )
                bJTKeywordsToDocOptionArray(a4, a3, v44, a6, v11 + 49);
            }
          }
        }
      }
    }
    v48 = v11[35];
    if ( !v48 || v48 > *(_DWORD *)(a3 + 80) )
      v11[35] = *(_DWORD *)(a3 + 80);
    if ( v11[32] == 3 && *(_DWORD *)(a3 + 112) != 2 )
      v11[32] = 0;
    if ( (*(_BYTE *)(a3 + 140) & 8) != 0 )
      v11[1] &= ~0x10u;
    if ( DoesFullPathMatchFile(*(const unsigned __int16 **)(v44 + 40), L"PrintConfig.dll") )
    {
      v49 = *(_DWORD *)(a3 + 304);
      if ( v49 )
      {
        v50 = *(_DWORD *)(a3 + 308);
        if ( v50 )
        {
          v51 = -1;
          do
            ++v51;
          while ( *((_WORD *)v11 + v51 + 362) );
          if ( !(_DWORD)v51 )
            goto LABEL_126;
          if ( (unsigned int)v51 >= v49 && (unsigned int)v51 <= v50 )
          {
            v37 = 0;
            while ( (unsigned __int16)(*((_WORD *)v11 + (unsigned int)v37 + 362) - 48) <= 9u )
            {
              v37 = (unsigned int)(v37 + 1);
              if ( (unsigned int)v37 >= (unsigned int)v51 )
                goto LABEL_126;
            }
          }
        }
      }
      v52 = *(unsigned __int16 *)(a1 + 68);
      if ( v52 + a1 + 756 <= a1 + v52 + (unsigned __int64)*(unsigned __int16 *)(a1 + 70) )
      {
        *(_DWORD *)(v52 + a1 + 4) &= ~0x8000u;
        *(_OWORD *)(v52 + a1 + 724) = 0;
        *(_OWORD *)(v52 + a1 + 740) = 0;
      }
    }
  }
LABEL_126:
  if ( (*(_BYTE *)(a3 + 140) & 0x20) != 0 )
    BValidateCustomPageSizeData(a4, v11 + 38, v37, v20);
  return 1;
}

```

## disassembly

```asm
0x180028c30  push    rbx
0x180028c32  push    rbp
0x180028c33  push    rsi
0x180028c34  push    rdi
0x180028c35  push    r12
0x180028c37  push    r13
0x180028c39  push    r14
0x180028c3b  push    r15
0x180028c3d  sub     rsp, 58h
0x180028c41  mov     rdi, [rsp+98h+arg_30]
0x180028c49  xor     r11d, r11d
0x180028c4c  movzx   r15d, word ptr [rcx+44h]
0x180028c51  mov     r12, r9
0x180028c54  add     r15, rcx
0x180028c57  mov     rsi, r8
0x180028c5a  mov     rbx, rcx
0x180028c5d  movzx   r13d, word ptr [rdi+44h]
0x180028c62  add     r13, rdi
0x180028c65  cmp     [r9+3Ch], r11d
0x180028c69  jz      short loc_180028C74
0x180028c6b  mov     ebp, [r9+3Ch]
0x180028c6f  add     rbp, r9
0x180028c72  jmp     short loc_180028C77
0x180028c74  mov     rbp, r11
0x180028c77  mov     r10d, 1
0x180028c7d  cmp     [r8+12Ch], r11d
0x180028c84  jnz     short loc_180028CA4
0x180028c86  test    byte ptr [rdi+48h], 40h
0x180028c8a  jz      short loc_180028CA4
0x180028c8c  mov     ecx, [rdi+0B4h]
0x180028c92  lea     eax, [rcx-1]
0x180028c95  cmp     eax, r10d
0x180028c98  ja      short loc_180028CA4
0x180028c9a  or      dword ptr [rbx+48h], 40h
0x180028c9e  mov     [rbx+0B4h], ecx
0x180028ca4  mov     ecx, 200h
0x180028ca9  mov     edx, 100h
0x180028cae  test    [rdi+48h], ecx
0x180028cb1  jz      short loc_180028CD2
0x180028cb3  movzx   eax, word ptr [rdi+58h]
0x180028cb7  sub     ax, r10w
0x180028cbb  cmp     ax, 0Eh
0x180028cbf  jbe     short loc_180028CC7
0x180028cc1  cmp     [rdi+58h], dx
0x180028cc5  jl      short loc_180028CD2
0x180028cc7  or      [rbx+48h], ecx
0x180028cca  movzx   eax, word ptr [rdi+58h]
0x180028cce  mov     [rbx+58h], ax
0x180028cd2  test    [rdi+48h], r10b
0x180028cd6  jz      short loc_180028D23
0x180028cd8  movzx   r14d, word ptr [rdi+4Ch]
0x180028cdd  movzx   eax, r14w
0x180028ce1  sub     ax, r10w
0x180028ce5  cmp     ax, r10w
0x180028ce9  ja      short loc_180028D23
0x180028ceb  cmp     [r8+12Ch], r11d
0x180028cf2  jz      short loc_180028D1A
0x180028cf4  lea     r9, [rsp+98h+arg_8]
0x180028cfc  mov     r8d, r10d
0x180028cff  lea     rdx, kstrSchema_Orientation; "PageOrientation"
0x180028d06  mov     rcx, rsi
0x180028d09  call    PInternalGetKeywordMatchFeature
0x180028d0e  xor     r11d, r11d
0x180028d11  lea     r10d, [r11+1]
0x180028d15  test    rax, rax
0x180028d18  jz      short loc_180028D23
0x180028d1a  or      [rbx+48h], r10d
0x180028d1e  mov     [rbx+4Ch], r14w
0x180028d23  mov     eax, [rdi+48h]
0x180028d26  and     eax, 0Ch
0x180028d29  cmp     al, 0Ch
0x180028d2b  jnz     short loc_180028D87
0x180028d2d  cmp     [rdi+52h], r11w
0x180028d32  jle     short loc_180028D87
0x180028d34  cmp     [rdi+50h], r11w
0x180028d39  jle     short loc_180028D87
0x180028d3b  mov     ecx, [rbx+48h]
0x180028d3e  mov     r14d, 2
0x180028d44  and     ecx, 0FFFEFFFDh
0x180028d4a  mov     r9d, 100h
0x180028d50  or      ecx, 0Ch
0x180028d53  mov     [rbx+48h], ecx
0x180028d56  movzx   eax, word ptr [rdi+52h]
0x180028d5a  mov     [rbx+52h], ax
0x180028d5e  movzx   eax, word ptr [rdi+50h]
0x180028d62  mov     [rbx+50h], ax
0x180028d66  test    [rdi+48h], r14b
0x180028d6a  jz      loc_180028DF6
0x180028d70  cmp     [rdi+4Eh], r9w
0x180028d75  jnz     short loc_180028DF6
0x180028d77  or      ecx, r14d
0x180028d7a  mov     [rbx+48h], ecx
0x180028d7d  movzx   eax, word ptr [rdi+4Eh]
0x180028d81  mov     [rbx+4Eh], ax
0x180028d85  jmp     short loc_180028DF6
0x180028d87  mov     r14d, 2
0x180028d8d  test    [rdi+48h], r14b
0x180028d91  jz      short loc_180028DCE
0x180028d93  mov     eax, 7FFFh
0x180028d98  cmp     [rdi+4Eh], ax
0x180028d9c  jnz     short loc_180028DB6
0x180028d9e  test    byte ptr [rsi+8Ch], 20h
0x180028da5  jz      short loc_180028DF0
0x180028da7  cmp     dword ptr [rsi+10h], 40003h
0x180028dae  jnb     short loc_180028DB6
0x180028db0  test    [rbp+2Ch], r14b
0x180028db4  jz      short loc_180028DF0
0x180028db6  mov     eax, [rbx+48h]
0x180028db9  and     eax, 0FFFEFFF3h
0x180028dbe  or      eax, r14d
0x180028dc1  mov     [rbx+48h], eax
0x180028dc4  movzx   eax, word ptr [rdi+4Eh]
0x180028dc8  mov     [rbx+4Eh], ax
0x180028dcc  jmp     short loc_180028DF0
0x180028dce  mov     ecx, 10000h
0x180028dd3  test    [rdi+48h], ecx
0x180028dd6  jz      short loc_180028DF0
0x180028dd8  mov     eax, [rbx+48h]
0x180028ddb  lea     rdx, [rdi+66h]
0x180028ddf  and     eax, 0FFFFFFF1h
0x180028de2  or      eax, ecx
0x180028de4  lea     rcx, [rbx+66h]
0x180028de8  mov     [rbx+48h], eax
0x180028deb  call    CopyStringW
0x180028df0  mov     r9d, 100h
0x180028df6  cmp     [rsi+12Ch], r11d
0x180028dfd  jnz     short loc_180028E23
0x180028dff  test    byte ptr [rdi+48h], 10h
0x180028e03  jz      short loc_180028E23
0x180028e05  movzx   eax, word ptr [rdi+54h]
0x180028e09  mov     ecx, 3E7h
0x180028e0e  sub     ax, r10w
0x180028e12  cmp     ax, cx
0x180028e15  ja      short loc_180028E23
0x180028e17  or      dword ptr [rbx+48h], 10h
0x180028e1b  movzx   eax, word ptr [rdi+54h]
0x180028e1f  mov     [rbx+54h], ax
0x180028e23  test    [rdi+48h], r9d
0x180028e27  jz      short loc_180028E45
0x180028e29  movzx   eax, word ptr [rdi+56h]
0x180028e2d  cmp     ax, r10w
0x180028e31  jl      short loc_180028E45
0x180028e33  cmp     ax, [rsi+3Ch]
0x180028e37  jg      short loc_180028E45
0x180028e39  or      [rbx+48h], r9d
0x180028e3d  movzx   eax, word ptr [rdi+56h]
0x180028e41  mov     [rbx+56h], ax
0x180028e45  mov     edx, [rdi+48h]
0x180028e48  mov     r8d, 1000h
0x180028e4e  test    r8d, edx
0x180028e51  jz      short loc_180028E86
0x180028e53  mov     eax, [rsi+0D8h]
0x180028e59  test    eax, eax
0x180028e5b  jz      short loc_180028E86
0x180028e5d  mov     rcx, [rsi+148h]
0x180028e64  add     rcx, rax
0x180028e67  jz      short loc_180028E86
0x180028e69  movzx   eax, word ptr [rdi+5Eh]
0x180028e6d  sub     ax, r10w
0x180028e71  cmp     ax, r14w
0x180028e75  ja      short loc_180028E86
0x180028e77  or      [rbx+48h], r8d
0x180028e7b  movzx   eax, word ptr [rdi+5Eh]
0x180028e7f  mov     [rbx+5Eh], ax
0x180028e83  mov     edx, [rdi+48h]
0x180028e86  cmp     [rsi+12Ch], r11d
0x180028e8d  jnz     short loc_180028EAD
0x180028e8f  mov     eax, 8000h
0x180028e94  test    eax, edx
0x180028e96  jz      short loc_180028EAD
0x180028e98  cmp     [rdi+64h], r10w
0x180028e9d  ja      short loc_180028EAD
0x180028e9f  or      [rbx+48h], eax
0x180028ea2  movzx   eax, word ptr [rdi+64h]
0x180028ea6  mov     [rbx+64h], ax
0x180028eaa  mov     edx, [rdi+48h]
0x180028ead  mov     r8d, 3
0x180028eb3  cmp     [rsi+12Ch], r11d
0x180028eba  jnz     short loc_180028EEF
0x180028ebc  mov     ecx, 4000h
0x180028ec1  test    ecx, edx
0x180028ec3  jz      short loc_180028EEF
0x180028ec5  movzx   eax, word ptr [rdi+62h]
0x180028ec9  sub     ax, r10w
0x180028ecd  cmp     ax, r14w
0x180028ed1  ja      short loc_180028EEF
0x180028ed3  or      [rbx+48h], ecx
0x180028ed6  movzx   eax, word ptr [rdi+62h]
0x180028eda  sub     ax, r8w
0x180028ede  neg     ax
0x180028ee1  sbb     ax, ax
0x180028ee4  add     ax, r8w
0x180028ee8  mov     [rbx+62h], ax
0x180028eec  mov     edx, [rdi+48h]
0x180028eef  test    byte ptr [rsi+8Ch], 8
0x180028ef6  jz      loc_180028F82
0x180028efc  mov     ecx, 800h
0x180028f01  test    ecx, edx
0x180028f03  jz      short loc_180028F21
0x180028f05  movzx   eax, word ptr [rdi+5Ch]
0x180028f09  sub     ax, r10w
0x180028f0d  cmp     ax, r10w
0x180028f11  ja      short loc_180028F21
0x180028f13  or      [rbx+48h], ecx
0x180028f16  movzx   eax, word ptr [rdi+5Ch]
0x180028f1a  mov     [rbx+5Ch], ax
0x180028f1e  mov     edx, [rdi+48h]
0x180028f21  cmp     [rsi+12Ch], r11d
0x180028f28  jnz     short loc_180028F82
0x180028f2a  mov     ecx, 800000h
0x180028f2f  test    ecx, edx
0x180028f31  jz      short loc_180028F53
0x180028f33  mov     eax, [rdi+0BCh]
0x180028f39  sub     eax, r10d
0x180028f3c  cmp     eax, r8d
0x180028f3f  ja      short loc_180028F53
0x180028f41  or      [rbx+48h], ecx
0x180028f44  mov     eax, [rdi+0BCh]
0x180028f4a  mov     [rbx+0BCh], eax
0x180028f50  mov     edx, [rdi+48h]
0x180028f53  cmp     [rsi+12Ch], r11d
0x180028f5a  jnz     short loc_180028F82
0x180028f5c  mov     ecx, 1000000h
0x180028f61  test    ecx, edx
0x180028f63  jz      short loc_180028F82
0x180028f65  mov     eax, [rdi+0C0h]
0x180028f6b  sub     eax, r10d
0x180028f6e  cmp     eax, r8d
0x180028f71  ja      short loc_180028F82
0x180028f73  or      [rbx+48h], ecx
0x180028f76  mov     eax, [rdi+0C0h]
0x180028f7c  mov     [rbx+0C0h], eax
0x180028f82  mov     edx, [rdi+48h]
0x180028f85  and     edx, 2400h
0x180028f8b  jz      loc_18002904C
0x180028f91  mov     eax, [rsi+0CCh]
0x180028f97  test    eax, eax
0x180028f99  jz      loc_18002904C
0x180028f9f  mov     ebp, eax
0x180028fa1  mov     rax, [rsi+148h]
0x180028fa8  add     rbp, rax
0x180028fab  jz      loc_18002904C
0x180028fb1  cmp     edx, 400h
0x180028fb7  jz      short loc_180028FCD
0x180028fb9  movzx   r8d, word ptr [rdi+60h]
0x180028fbe  cmp     edx, 2000h
0x180028fc4  jz      short loc_180028FD2
0x180028fc6  movzx   r10d, word ptr [rdi+5Ah]
0x180028fcb  jmp     short loc_180028FD6
0x180028fcd  movzx   r8d, word ptr [rdi+5Ah]
0x180028fd2  movzx   r10d, r8w
0x180028fd6  cmp     [rax+38h], r11d
0x180028fda  jz      short loc_180028FE4
0x180028fdc  mov     ecx, [rax+38h]
0x180028fdf  add     rcx, rax
0x180028fe2  jmp     short loc_180028FE7
0x180028fe4  mov     rcx, r11
0x180028fe7  mov     eax, [rcx+0CCh]
0x180028fed  test    eax, eax
0x180028fef  jz      short loc_180029019
0x180028ff1  mov     edx, eax
0x180028ff3  add     rdx, [rcx+148h]
0x180028ffa  jz      short loc_180029019
0x180028ffc  movsx   r9d, r8w
0x180029000  movsx   r8d, r10w
0x180029004  mov     [rsp+98h+var_78], r11
0x180029009  call    DwInternalMapToOptIndex
0x18002900e  xor     r11d, r11d
0x180029011  mov     r9d, 100h
0x180029017  jmp     short loc_18002901E
0x180029019  mov     eax, 0FFh
0x18002901e  cmp     eax, [rbp+34h]
0x180029021  jnb     short loc_18002904C
0x180029023  imul    eax, [rbp+30h]
0x180029027  add     eax, [rbp+38h]
0x18002902a  mov     edx, eax
0x18002902c  add     rdx, [rsi+148h]
0x180029033  jz      short loc_18002904C
0x180029035  or      dword ptr [rbx+48h], 2400h
0x18002903c  movzx   eax, word ptr [rdx+38h]
0x180029040  mov     [rbx+5Ah], ax
0x180029044  movzx   eax, word ptr [rdx+3Ch]
0x180029048  mov     [rbx+60h], ax
0x18002904c  mov     r8d, 2000000h
0x180029052  test    [rdi+48h], r8d
0x180029056  jz      short loc_18002909B
0x180029058  mov     eax, [rsi+0E0h]
0x18002905e  test    eax, eax
0x180029060  jz      short loc_18002909B
0x180029062  mov     rdx, [rsi+148h]
0x180029069  add     rdx, rax
0x18002906c  jz      short loc_18002909B
0x18002906e  mov     ecx, [rdi+0C4h]
0x180029074  lea     eax, [rcx-1]
0x180029077  cmp     eax, r14d
0x18002907a  jbe     short loc_18002908B
0x18002907c  cmp     ecx, r9d
0x18002907f  jb      short loc_18002909B
0x180029081  mov     eax, [rdx+34h]
0x180029084  add     eax, r9d
  ... truncated ...
```
