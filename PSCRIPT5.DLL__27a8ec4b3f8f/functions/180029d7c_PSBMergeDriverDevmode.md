# PSBMergeDriverDevmode

- ea: `0x180029d7c`
- end: `0x18002a48e`
- name: `PSBMergeDriverDevmode`
- size: `1810`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, __int64, __int64, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180032054`

## callees

- `0x180029d7c`
- `0x18002f1b4`
- `0x180030c20`
- `0x180031044`
- `0x180034774`
- `0x180036224`
- `0x180055440`
- `0x1800559f4`
- `0x18005dbe8`

## string_xrefs

- `0x18002a3bc`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall PSBMergeDriverDevmode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5,
        const wchar_t *a6,
        __int64 a7,
        _WORD *a8)
{
  __int64 v8; // rdi
  unsigned int *v9; // r11
  __int64 v11; // r15
  _OWORD *v14; // r13
  char *v15; // rbp
  int v16; // r10d
  int v17; // ecx
  __int16 v18; // r14
  unsigned int *KeywordMatchFeature; // rax
  unsigned int v20; // ecx
  __int16 v21; // ax
  int v22; // edx
  __int64 v23; // rax
  int v24; // edx
  unsigned int v25; // eax
  __int64 v26; // rbp
  __int64 v27; // rax
  _DWORD *v28; // rbp
  __int16 v29; // r8
  __int16 v30; // r10
  __int64 v31; // rcx
  unsigned int v32; // eax
  _DWORD *v33; // rdx
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rdx
  unsigned int v39; // ecx
  __int64 v40; // rax
  _OWORD *v41; // rcx
  __int128 v42; // xmm1
  __int64 v43; // rbp
  __int64 v44; // rdx
  unsigned __int16 v45; // cx
  unsigned __int16 v46; // r8
  int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // ecx
  __int64 v50; // rdx
  unsigned int v51; // r8d
  __int64 v52; // rdx
  __int64 v54; // [rsp+28h] [rbp-70h]
  unsigned int v55; // [rsp+A8h] [rbp+10h] BYREF

  v8 = a7;
  v9 = 0;
  v11 = a1 + *(unsigned __int16 *)(a1 + 68);
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
        || (KeywordMatchFeature = PInternalGetKeywordMatchFeature(a3, "PageOrientation", 1, &v55),
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
    v20 = *(_DWORD *)(a1 + 72) & 0xFFFEFFF1 | 0xC;
    *(_DWORD *)(a1 + 72) = v20;
    *(_WORD *)(a1 + 82) = *(_WORD *)(v8 + 82);
    *(_WORD *)(a1 + 80) = *(_WORD *)(v8 + 80);
    if ( (*(_BYTE *)(v8 + 72) & 2) != 0 && *(_WORD *)(v8 + 78) == 256 )
    {
      *(_DWORD *)(a1 + 72) = v20 | 2;
      *(_WORD *)(a1 + 78) = *(_WORD *)(v8 + 78);
    }
  }
  else if ( (*(_BYTE *)(v8 + 72) & 2) != 0 )
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
    CopyStringW((char *)(a1 + 102), (__int16 *)(v8 + 102));
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
    v21 = *(_WORD *)(v8 + 86);
    if ( v21 >= (__int16)v16 && v21 <= *(__int16 *)(a3 + 60) )
    {
      *(_DWORD *)(a1 + 72) |= 0x100u;
      *(_WORD *)(a1 + 86) = *(_WORD *)(v8 + 86);
    }
  }
  v22 = *(_DWORD *)(v8 + 72);
  if ( (v22 & 0x1000) != 0 )
  {
    v23 = *(unsigned int *)(a3 + 216);
    if ( (_DWORD)v23 )
    {
      if ( v23 + *(_QWORD *)(a3 + 328) && (unsigned __int16)(*(_WORD *)(v8 + 94) - v16) <= 2u )
      {
        *(_DWORD *)(a1 + 72) |= 0x1000u;
        *(_WORD *)(a1 + 94) = *(_WORD *)(v8 + 94);
        v22 = *(_DWORD *)(v8 + 72);
      }
    }
  }
  if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9 && (v22 & 0x8000) != 0 && *(_WORD *)(v8 + 100) <= (unsigned __int16)v16 )
  {
    *(_DWORD *)(a1 + 72) |= 0x8000u;
    *(_WORD *)(a1 + 100) = *(_WORD *)(v8 + 100);
    v22 = *(_DWORD *)(v8 + 72);
  }
  if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9 && (v22 & 0x4000) != 0 && (unsigned __int16)(*(_WORD *)(v8 + 98) - v16) <= 2u )
  {
    *(_DWORD *)(a1 + 72) |= 0x4000u;
    *(_WORD *)(a1 + 98) = 3 - (*(_WORD *)(v8 + 98) != 3);
    v22 = *(_DWORD *)(v8 + 72);
  }
  if ( (*(_BYTE *)(a3 + 140) & 8) != 0 )
  {
    if ( (v22 & 0x800) != 0 && (unsigned __int16)(*(_WORD *)(v8 + 92) - v16) <= (unsigned __int16)v16 )
    {
      *(_DWORD *)(a1 + 72) |= 0x800u;
      *(_WORD *)(a1 + 92) = *(_WORD *)(v8 + 92);
      v22 = *(_DWORD *)(v8 + 72);
    }
    if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9 )
    {
      if ( (v22 & 0x800000) != 0 && (unsigned int)(*(_DWORD *)(v8 + 188) - v16) <= 3 )
      {
        *(_DWORD *)(a1 + 72) |= 0x800000u;
        *(_DWORD *)(a1 + 188) = *(_DWORD *)(v8 + 188);
        v22 = *(_DWORD *)(v8 + 72);
      }
      if ( *(_DWORD *)(a3 + 300) == (_DWORD)v9
        && (v22 & 0x1000000) != 0
        && (unsigned int)(*(_DWORD *)(v8 + 192) - v16) <= 3 )
      {
        *(_DWORD *)(a1 + 72) |= 0x1000000u;
        *(_DWORD *)(a1 + 192) = *(_DWORD *)(v8 + 192);
      }
    }
  }
  v24 = *(_DWORD *)(v8 + 72) & 0x2400;
  if ( v24 )
  {
    v25 = *(_DWORD *)(a3 + 204);
    if ( v25 )
    {
      v26 = v25;
      v27 = *(_QWORD *)(a3 + 328);
      v28 = (_DWORD *)(v27 + v26);
      if ( v28 )
      {
        if ( v24 == 1024 )
        {
          v29 = *(_WORD *)(v8 + 90);
        }
        else
        {
          v29 = *(_WORD *)(v8 + 96);
          if ( v24 != 0x2000 )
          {
            v30 = *(_WORD *)(v8 + 90);
            goto LABEL_72;
          }
        }
        v30 = v29;
LABEL_72:
        if ( *(_DWORD *)(v27 + 56) == (_DWORD)v9 )
          v31 = (__int64)v9;
        else
          v31 = v27 + *(unsigned int *)(v27 + 56);
        v32 = *(_DWORD *)(v31 + 204);
        if ( v32 && (v33 = (_DWORD *)(*(_QWORD *)(v31 + 328) + v32)) != 0 )
        {
          v34 = DwInternalMapToOptIndex(v31, v33, v30, v29, v9);
          LODWORD(v9) = 0;
        }
        else
        {
          v34 = 255;
        }
        if ( v34 < v28[13] )
        {
          v35 = *(_QWORD *)(a3 + 328) + v28[14] + v28[12] * v34;
          if ( v35 )
          {
            *(_DWORD *)(a1 + 72) |= 0x2400u;
            *(_WORD *)(a1 + 90) = *(_WORD *)(v35 + 56);
            *(_WORD *)(a1 + 96) = *(_WORD *)(v35 + 60);
          }
        }
      }
    }
  }
  v36 = 0x2000000;
  if ( (*(_DWORD *)(v8 + 72) & 0x2000000) != 0 )
  {
    v37 = *(unsigned int *)(a3 + 224);
    if ( (_DWORD)v37 )
    {
      v38 = v37 + *(_QWORD *)(a3 + 328);
      if ( v38 )
      {
        v39 = *(_DWORD *)(v8 + 196);
        if ( v39 - 1 <= 2 || v39 >= 0x100 && v39 < *(_DWORD *)(v38 + 52) + 256 )
        {
          *(_DWORD *)(a1 + 72) |= 0x2000000u;
          *(_DWORD *)(a1 + 196) = *(_DWORD *)(v8 + 196);
        }
      }
    }
  }
  if ( *(_DWORD *)(a3 + 300) != (_DWORD)v9 )
    VMergeXPSDevmode(a3, v8, a1);
  if ( *(_DWORD *)v14 == 1447645776 )
  {
    v40 = 5;
    v41 = (_OWORD *)v11;
    do
    {
      *v41 = *v14;
      v41[1] = v14[1];
      v41[2] = v14[2];
      v41[3] = v14[3];
      v41[4] = v14[4];
      v41[5] = v14[5];
      v41[6] = v14[6];
      v42 = v14[7];
      v14 += 8;
      v41[7] = v42;
      v41 += 8;
      --v40;
    }
    while ( v40 );
    v43 = a5;
    *v41 = *v14;
    v41[1] = v14[1];
    v41[2] = v14[2];
    v41[3] = v14[3];
    v41[4] = v14[4];
    v41[5] = v14[5];
    v41[6] = v14[6];
    *((_DWORD *)v41 + 28) = *((_DWORD *)v14 + 28);
    if ( *(_DWORD *)(v11 + 188) != a4[3] )
    {
      InitDefaultOptions(a4, (void *)(v11 + 196), v36, 0);
      *(_DWORD *)(v11 + 192) = a4[5];
      *(_DWORD *)(v11 + 188) = a4[3];
      if ( a8[33] >= 0x600u && a8[35] > 0x2C4u )
      {
        v44 = (unsigned __int16)a8[34];
        if ( *(_DWORD *)((char *)a8 + v44) == 1447645776 )
        {
          v45 = *(_WORD *)((char *)a8 + v44 + 114);
          if ( v45 > 0x2C4u )
          {
            v46 = *(_WORD *)((char *)a8 + v44 + 112);
            if ( v46 )
            {
              if ( v45 > v46 && a8[35] >= v45 )
                bJTKeywordsToDocOptionArray((__int64)a4, a3, v43, a6, v11 + 196, v54, (__int64)a8, v45, v46);
            }
          }
        }
      }
    }
    v47 = *(_DWORD *)(v11 + 140);
    if ( !v47 || v47 > *(_DWORD *)(a3 + 80) )
      *(_DWORD *)(v11 + 140) = *(_DWORD *)(a3 + 80);
    if ( *(_DWORD *)(v11 + 128) == 3 && *(_DWORD *)(a3 + 112) != 2 )
      *(_DWORD *)(v11 + 128) = 0;
    if ( (*(_BYTE *)(a3 + 140) & 8) != 0 )
      *(_DWORD *)(v11 + 4) &= ~0x10u;
    if ( DoesFullPathMatchFile(*(const unsigned __int16 **)(v43 + 40), L"PrintConfig.dll") )
    {
      v48 = *(_DWORD *)(a3 + 304);
      if ( v48 )
      {
        v49 = *(_DWORD *)(a3 + 308);
        if ( v49 )
        {
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)(v11 + 2 * v50 + 724) );
          if ( !(_DWORD)v50 )
            goto LABEL_125;
          if ( (unsigned int)v50 >= v48 && (unsigned int)v50 <= v49 )
          {
            v51 = 0;
            while ( (unsigned __int16)(*(_WORD *)(v11 + 2LL * v51 + 724) - 48) <= 9u )
            {
              if ( ++v51 >= (unsigned int)v50 )
                goto LABEL_125;
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
LABEL_125:
  if ( (*(_BYTE *)(a3 + 140) & 0x20) != 0 )
    BValidateCustomPageSizeData((__int64)a4, (__int128 *)(v11 + 152));
  return 1;
}

```

## disassembly

```asm
0x180029d7c  push    rbx
0x180029d7e  push    rbp
0x180029d7f  push    rsi
0x180029d80  push    rdi
0x180029d81  push    r12
0x180029d83  push    r13
0x180029d85  push    r14
0x180029d87  push    r15
0x180029d89  sub     rsp, 58h
0x180029d8d  mov     rdi, [rsp+98h+arg_30]
0x180029d95  xor     r11d, r11d
0x180029d98  movzx   r15d, word ptr [rcx+44h]
0x180029d9d  mov     r12, r9
0x180029da0  add     r15, rcx
0x180029da3  mov     rsi, r8
0x180029da6  mov     rbx, rcx
0x180029da9  movzx   r13d, word ptr [rdi+44h]
0x180029dae  add     r13, rdi
0x180029db1  cmp     [r9+3Ch], r11d
0x180029db5  jz      short loc_180029DC0
0x180029db7  mov     ebp, [r9+3Ch]
0x180029dbb  add     rbp, r9
0x180029dbe  jmp     short loc_180029DC3
0x180029dc0  mov     rbp, r11
0x180029dc3  mov     r10d, 1
0x180029dc9  cmp     [r8+12Ch], r11d
0x180029dd0  jnz     short loc_180029DF0
0x180029dd2  test    byte ptr [rdi+48h], 40h
0x180029dd6  jz      short loc_180029DF0
0x180029dd8  mov     ecx, [rdi+0B4h]
0x180029dde  lea     eax, [rcx-1]
0x180029de1  cmp     eax, r10d
0x180029de4  ja      short loc_180029DF0
0x180029de6  or      dword ptr [rbx+48h], 40h
0x180029dea  mov     [rbx+0B4h], ecx
0x180029df0  mov     ecx, 200h
0x180029df5  mov     edx, 100h
0x180029dfa  test    [rdi+48h], ecx
0x180029dfd  jz      short loc_180029E1E
0x180029dff  movzx   eax, word ptr [rdi+58h]
0x180029e03  sub     ax, r10w
0x180029e07  cmp     ax, 0Eh
0x180029e0b  jbe     short loc_180029E13
0x180029e0d  cmp     [rdi+58h], dx
0x180029e11  jl      short loc_180029E1E
0x180029e13  or      [rbx+48h], ecx
0x180029e16  movzx   eax, word ptr [rdi+58h]
0x180029e1a  mov     [rbx+58h], ax
0x180029e1e  test    [rdi+48h], r10b
0x180029e22  jz      short loc_180029E6F
0x180029e24  movzx   r14d, word ptr [rdi+4Ch]
0x180029e29  movzx   eax, r14w
0x180029e2d  sub     ax, r10w
0x180029e31  cmp     ax, r10w
0x180029e35  ja      short loc_180029E6F
0x180029e37  cmp     [r8+12Ch], r11d
0x180029e3e  jz      short loc_180029E66
0x180029e40  lea     r9, [rsp+98h+arg_8]
0x180029e48  mov     r8d, r10d
0x180029e4b  lea     rdx, kstrSchema_Orientation; "PageOrientation"
0x180029e52  mov     rcx, rsi
0x180029e55  call    PInternalGetKeywordMatchFeature
0x180029e5a  xor     r11d, r11d
0x180029e5d  lea     r10d, [r11+1]
0x180029e61  test    rax, rax
0x180029e64  jz      short loc_180029E6F
0x180029e66  or      [rbx+48h], r10d
0x180029e6a  mov     [rbx+4Ch], r14w
0x180029e6f  mov     eax, [rdi+48h]
0x180029e72  and     eax, 0Ch
0x180029e75  cmp     al, 0Ch
0x180029e77  jnz     short loc_180029ED3
0x180029e79  cmp     [rdi+52h], r11w
0x180029e7e  jle     short loc_180029ED3
0x180029e80  cmp     [rdi+50h], r11w
0x180029e85  jle     short loc_180029ED3
0x180029e87  mov     ecx, [rbx+48h]
0x180029e8a  mov     r14d, 2
0x180029e90  and     ecx, 0FFFEFFFDh
0x180029e96  mov     r9d, 100h
0x180029e9c  or      ecx, 0Ch
0x180029e9f  mov     [rbx+48h], ecx
0x180029ea2  movzx   eax, word ptr [rdi+52h]
0x180029ea6  mov     [rbx+52h], ax
0x180029eaa  movzx   eax, word ptr [rdi+50h]
0x180029eae  mov     [rbx+50h], ax
0x180029eb2  test    [rdi+48h], r14b
0x180029eb6  jz      loc_180029F42
0x180029ebc  cmp     [rdi+4Eh], r9w
0x180029ec1  jnz     short loc_180029F42
0x180029ec3  or      ecx, r14d
0x180029ec6  mov     [rbx+48h], ecx
0x180029ec9  movzx   eax, word ptr [rdi+4Eh]
0x180029ecd  mov     [rbx+4Eh], ax
0x180029ed1  jmp     short loc_180029F42
0x180029ed3  mov     r14d, 2
0x180029ed9  test    [rdi+48h], r14b
0x180029edd  jz      short loc_180029F1A
0x180029edf  mov     eax, 7FFFh
0x180029ee4  cmp     [rdi+4Eh], ax
0x180029ee8  jnz     short loc_180029F02
0x180029eea  test    byte ptr [rsi+8Ch], 20h
0x180029ef1  jz      short loc_180029F3C
0x180029ef3  cmp     dword ptr [rsi+10h], 40003h
0x180029efa  jnb     short loc_180029F02
0x180029efc  test    [rbp+2Ch], r14b
0x180029f00  jz      short loc_180029F3C
0x180029f02  mov     eax, [rbx+48h]
0x180029f05  and     eax, 0FFFEFFF3h
0x180029f0a  or      eax, r14d
0x180029f0d  mov     [rbx+48h], eax
0x180029f10  movzx   eax, word ptr [rdi+4Eh]
0x180029f14  mov     [rbx+4Eh], ax
0x180029f18  jmp     short loc_180029F3C
0x180029f1a  mov     ecx, 10000h
0x180029f1f  test    [rdi+48h], ecx
0x180029f22  jz      short loc_180029F3C
0x180029f24  mov     eax, [rbx+48h]
0x180029f27  lea     rdx, [rdi+66h]
0x180029f2b  and     eax, 0FFFFFFF1h
0x180029f2e  or      eax, ecx
0x180029f30  lea     rcx, [rbx+66h]
0x180029f34  mov     [rbx+48h], eax
0x180029f37  call    CopyStringW
0x180029f3c  mov     r9d, 100h
0x180029f42  cmp     [rsi+12Ch], r11d
0x180029f49  jnz     short loc_180029F6F
0x180029f4b  test    byte ptr [rdi+48h], 10h
0x180029f4f  jz      short loc_180029F6F
0x180029f51  movzx   eax, word ptr [rdi+54h]
0x180029f55  mov     ecx, 3E7h
0x180029f5a  sub     ax, r10w
0x180029f5e  cmp     ax, cx
0x180029f61  ja      short loc_180029F6F
0x180029f63  or      dword ptr [rbx+48h], 10h
0x180029f67  movzx   eax, word ptr [rdi+54h]
0x180029f6b  mov     [rbx+54h], ax
0x180029f6f  test    [rdi+48h], r9d
0x180029f73  jz      short loc_180029F91
0x180029f75  movzx   eax, word ptr [rdi+56h]
0x180029f79  cmp     ax, r10w
0x180029f7d  jl      short loc_180029F91
0x180029f7f  cmp     ax, [rsi+3Ch]
0x180029f83  jg      short loc_180029F91
0x180029f85  or      [rbx+48h], r9d
0x180029f89  movzx   eax, word ptr [rdi+56h]
0x180029f8d  mov     [rbx+56h], ax
0x180029f91  mov     edx, [rdi+48h]
0x180029f94  mov     r8d, 1000h
0x180029f9a  test    r8d, edx
0x180029f9d  jz      short loc_180029FD2
0x180029f9f  mov     eax, [rsi+0D8h]
0x180029fa5  test    eax, eax
0x180029fa7  jz      short loc_180029FD2
0x180029fa9  mov     rcx, [rsi+148h]
0x180029fb0  add     rcx, rax
0x180029fb3  jz      short loc_180029FD2
0x180029fb5  movzx   eax, word ptr [rdi+5Eh]
0x180029fb9  sub     ax, r10w
0x180029fbd  cmp     ax, r14w
0x180029fc1  ja      short loc_180029FD2
0x180029fc3  or      [rbx+48h], r8d
0x180029fc7  movzx   eax, word ptr [rdi+5Eh]
0x180029fcb  mov     [rbx+5Eh], ax
0x180029fcf  mov     edx, [rdi+48h]
0x180029fd2  cmp     [rsi+12Ch], r11d
0x180029fd9  jnz     short loc_180029FF9
0x180029fdb  mov     eax, 8000h
0x180029fe0  test    eax, edx
0x180029fe2  jz      short loc_180029FF9
0x180029fe4  cmp     [rdi+64h], r10w
0x180029fe9  ja      short loc_180029FF9
0x180029feb  or      [rbx+48h], eax
0x180029fee  movzx   eax, word ptr [rdi+64h]
0x180029ff2  mov     [rbx+64h], ax
0x180029ff6  mov     edx, [rdi+48h]
0x180029ff9  mov     r8d, 3
0x180029fff  cmp     [rsi+12Ch], r11d
0x18002a006  jnz     short loc_18002A03B
0x18002a008  mov     ecx, 4000h
0x18002a00d  test    ecx, edx
0x18002a00f  jz      short loc_18002A03B
0x18002a011  movzx   eax, word ptr [rdi+62h]
0x18002a015  sub     ax, r10w
0x18002a019  cmp     ax, r14w
0x18002a01d  ja      short loc_18002A03B
0x18002a01f  or      [rbx+48h], ecx
0x18002a022  movzx   eax, word ptr [rdi+62h]
0x18002a026  sub     ax, r8w
0x18002a02a  neg     ax
0x18002a02d  sbb     ax, ax
0x18002a030  add     ax, r8w
0x18002a034  mov     [rbx+62h], ax
0x18002a038  mov     edx, [rdi+48h]
0x18002a03b  test    byte ptr [rsi+8Ch], 8
0x18002a042  jz      loc_18002A0CE
0x18002a048  mov     ecx, 800h
0x18002a04d  test    ecx, edx
0x18002a04f  jz      short loc_18002A06D
0x18002a051  movzx   eax, word ptr [rdi+5Ch]
0x18002a055  sub     ax, r10w
0x18002a059  cmp     ax, r10w
0x18002a05d  ja      short loc_18002A06D
0x18002a05f  or      [rbx+48h], ecx
0x18002a062  movzx   eax, word ptr [rdi+5Ch]
0x18002a066  mov     [rbx+5Ch], ax
0x18002a06a  mov     edx, [rdi+48h]
0x18002a06d  cmp     [rsi+12Ch], r11d
0x18002a074  jnz     short loc_18002A0CE
0x18002a076  mov     ecx, 800000h
0x18002a07b  test    ecx, edx
0x18002a07d  jz      short loc_18002A09F
0x18002a07f  mov     eax, [rdi+0BCh]
0x18002a085  sub     eax, r10d
0x18002a088  cmp     eax, r8d
0x18002a08b  ja      short loc_18002A09F
0x18002a08d  or      [rbx+48h], ecx
0x18002a090  mov     eax, [rdi+0BCh]
0x18002a096  mov     [rbx+0BCh], eax
0x18002a09c  mov     edx, [rdi+48h]
0x18002a09f  cmp     [rsi+12Ch], r11d
0x18002a0a6  jnz     short loc_18002A0CE
0x18002a0a8  mov     ecx, 1000000h
0x18002a0ad  test    ecx, edx
0x18002a0af  jz      short loc_18002A0CE
0x18002a0b1  mov     eax, [rdi+0C0h]
0x18002a0b7  sub     eax, r10d
0x18002a0ba  cmp     eax, r8d
0x18002a0bd  ja      short loc_18002A0CE
0x18002a0bf  or      [rbx+48h], ecx
0x18002a0c2  mov     eax, [rdi+0C0h]
0x18002a0c8  mov     [rbx+0C0h], eax
0x18002a0ce  mov     edx, [rdi+48h]
0x18002a0d1  and     edx, 2400h
0x18002a0d7  jz      loc_18002A198
0x18002a0dd  mov     eax, [rsi+0CCh]
0x18002a0e3  test    eax, eax
0x18002a0e5  jz      loc_18002A198
0x18002a0eb  mov     ebp, eax
0x18002a0ed  mov     rax, [rsi+148h]
0x18002a0f4  add     rbp, rax
0x18002a0f7  jz      loc_18002A198
0x18002a0fd  cmp     edx, 400h
0x18002a103  jz      short loc_18002A119
0x18002a105  movzx   r8d, word ptr [rdi+60h]
0x18002a10a  cmp     edx, 2000h
0x18002a110  jz      short loc_18002A11E
0x18002a112  movzx   r10d, word ptr [rdi+5Ah]
0x18002a117  jmp     short loc_18002A122
0x18002a119  movzx   r8d, word ptr [rdi+5Ah]
0x18002a11e  movzx   r10d, r8w
0x18002a122  cmp     [rax+38h], r11d
0x18002a126  jz      short loc_18002A130
0x18002a128  mov     ecx, [rax+38h]
0x18002a12b  add     rcx, rax
0x18002a12e  jmp     short loc_18002A133
0x18002a130  mov     rcx, r11
0x18002a133  mov     eax, [rcx+0CCh]
0x18002a139  test    eax, eax
0x18002a13b  jz      short loc_18002A165
0x18002a13d  mov     edx, eax
0x18002a13f  add     rdx, [rcx+148h]
0x18002a146  jz      short loc_18002A165
0x18002a148  movsx   r9d, r8w
0x18002a14c  movsx   r8d, r10w
0x18002a150  mov     [rsp+98h+var_78], r11
0x18002a155  call    DwInternalMapToOptIndex
0x18002a15a  xor     r11d, r11d
0x18002a15d  mov     r9d, 100h
0x18002a163  jmp     short loc_18002A16A
0x18002a165  mov     eax, 0FFh
0x18002a16a  cmp     eax, [rbp+34h]
0x18002a16d  jnb     short loc_18002A198
0x18002a16f  imul    eax, [rbp+30h]
0x18002a173  add     eax, [rbp+38h]
0x18002a176  mov     edx, eax
0x18002a178  add     rdx, [rsi+148h]
0x18002a17f  jz      short loc_18002A198
0x18002a181  or      dword ptr [rbx+48h], 2400h
0x18002a188  movzx   eax, word ptr [rdx+38h]
0x18002a18c  mov     [rbx+5Ah], ax
0x18002a190  movzx   eax, word ptr [rdx+3Ch]
0x18002a194  mov     [rbx+60h], ax
0x18002a198  mov     r8d, 2000000h
0x18002a19e  test    [rdi+48h], r8d
0x18002a1a2  jz      short loc_18002A1E7
0x18002a1a4  mov     eax, [rsi+0E0h]
0x18002a1aa  test    eax, eax
0x18002a1ac  jz      short loc_18002A1E7
0x18002a1ae  mov     rdx, [rsi+148h]
0x18002a1b5  add     rdx, rax
0x18002a1b8  jz      short loc_18002A1E7
0x18002a1ba  mov     ecx, [rdi+0C4h]
0x18002a1c0  lea     eax, [rcx-1]
0x18002a1c3  cmp     eax, r14d
0x18002a1c6  jbe     short loc_18002A1D7
0x18002a1c8  cmp     ecx, r9d
0x18002a1cb  jb      short loc_18002A1E7
0x18002a1cd  mov     eax, [rdx+34h]
0x18002a1d0  add     eax, r9d
  ... truncated ...
```
