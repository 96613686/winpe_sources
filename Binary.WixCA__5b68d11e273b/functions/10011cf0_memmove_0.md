# _memmove_0

- ea: `0x10011cf0`
- end: `0x10012264`
- name: `_memmove_0`
- size: `1396`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1000a57a`
- `0x1000c6bd`
- `0x10018161`
- `0x100185c3`
- `0x1001b876`

## callees

- `0x10011cf0`

## pseudocode

```c
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  const __m128i *v3; // esi
  size_t v4; // ecx
  __m128i *v5; // edi
  void *result; // eax
  __int64 v7; // xmm1_8
  __m128i v8; // xmm1
  const __m128i *v9; // esi
  __m128i v10; // xmm3
  __m128i v11; // xmm0
  __m128i v12; // xmm5
  const __m128i *v13; // esi
  __m128i v14; // xmm1
  const __m128i *v15; // esi
  __m128i v16; // xmm3
  __m128i v17; // xmm0
  __m128i v18; // xmm5
  __m128i v19; // xmm1
  const __m128i *v20; // esi
  __m128i v21; // xmm3
  __m128i v22; // xmm0
  __m128i v23; // xmm5
  __m128i v24; // xmm1
  __int32 v25; // eax
  __int64 v26; // xmm1_8
  char v27; // dl
  size_t v28; // ecx
  const __m128i *v29; // esi
  __m128i *v30; // edi
  int v31; // edx
  char v32; // dl
  size_t v33; // ecx
  int v34; // edx
  __int8 *v35; // esi
  char *v36; // edi
  __m128i v37; // xmm1
  __m128i v38; // xmm2
  __m128i v39; // xmm3
  __m128i v40; // xmm4
  __m128i v41; // xmm5
  __m128i v42; // xmm6
  __m128i v43; // xmm7
  __m128i v44; // xmm1
  int v45; // eax
  size_t v46; // edx
  size_t j; // edx
  __m128i si128; // xmm1
  __m128i v49; // xmm2
  __m128i v50; // xmm3
  __m128i v51; // xmm5
  __m128i v52; // xmm6
  __m128i v53; // xmm7
  size_t k; // edx
  __m128i v55; // xmm1
  unsigned int v56; // ecx
  char v57; // al
  unsigned int m; // ecx
  int v59; // ecx
  unsigned int v60; // eax
  int v61; // ecx
  unsigned int i; // eax
  size_t v63; // [esp-4h] [ebp-Ch]

  v3 = (const __m128i *)Src;
  v4 = Size;
  v5 = (__m128i *)a1;
  if ( a1 > Src && a1 < (char *)Src + Size )
  {
    v29 = (const __m128i *)((char *)Src + Size);
    v30 = (__m128i *)((char *)a1 + Size);
    if ( Size >= 0x20 )
    {
      if ( _bittest(&dword_10033060, 1u) )
      {
        for ( ; ((unsigned __int8)v30 & 0xF) != 0; v30->m128i_i8[0] = v29->m128i_i8[0] )
        {
          --v4;
          v29 = (const __m128i *)((char *)v29 - 1);
          v30 = (__m128i *)((char *)v30 - 1);
        }
        do
        {
          if ( v4 < 0x80 )
            break;
          v29 -= 8;
          v30 -= 8;
          v37 = _mm_loadu_si128(v29 + 1);
          v38 = _mm_loadu_si128(v29 + 2);
          v39 = _mm_loadu_si128(v29 + 3);
          v40 = _mm_loadu_si128(v29 + 4);
          v41 = _mm_loadu_si128(v29 + 5);
          v42 = _mm_loadu_si128(v29 + 6);
          v43 = _mm_loadu_si128(v29 + 7);
          *v30 = _mm_loadu_si128(v29);
          v30[1] = v37;
          v30[2] = v38;
          v30[3] = v39;
          v30[4] = v40;
          v30[5] = v41;
          v30[6] = v42;
          v30[7] = v43;
          v4 -= 128;
        }
        while ( (v4 & 0xFFFFFF80) != 0 );
        if ( v4 >= 0x20 )
        {
          do
          {
            v29 -= 2;
            v30 -= 2;
            v44 = _mm_loadu_si128(v29 + 1);
            *v30 = _mm_loadu_si128(v29);
            v30[1] = v44;
            v4 -= 32;
          }
          while ( (v4 & 0xFFFFFFE0) != 0 );
        }
      }
      else
      {
        if ( ((unsigned __int8)v30 & 3) != 0 )
        {
          v31 = (unsigned __int8)v30 & 3;
          v4 = Size - v31;
          do
          {
            v30[-1].m128i_i8[15] = v29[-1].m128i_i8[15];
            v29 = (const __m128i *)((char *)v29 - 1);
            v30 = (__m128i *)((char *)v30 - 1);
            --v31;
          }
          while ( v31 );
        }
        if ( v4 >= 0x20 )
        {
          v32 = v4;
          v33 = v4 >> 2;
          v34 = v32 & 3;
          v35 = &v29[-1].m128i_i8[12];
          v36 = &v30[-1].m128i_i8[12];
          while ( v33 )
          {
            *(_DWORD *)v36 = *(_DWORD *)v35;
            v35 -= 4;
            v36 -= 4;
            --v33;
          }
          switch ( v34 )
          {
            case 0:
              result = a1;
              break;
            case 1:
              v36[3] = v35[3];
              result = a1;
              break;
            case 2:
              v36[3] = v35[3];
              v36[2] = v35[2];
              result = a1;
              break;
            case 3:
              v36[3] = v35[3];
              v36[2] = v35[2];
              v36[1] = v35[1];
              result = a1;
              break;
          }
          return result;
        }
      }
    }
    for ( ; (v4 & 0xFFFFFFFC) != 0; v4 -= 4 )
    {
      v30 = (__m128i *)((char *)v30 - 4);
      v29 = (const __m128i *)((char *)v29 - 4);
      v30->m128i_i32[0] = v29->m128i_i32[0];
    }
    for ( ; v4; --v4 )
    {
      v30 = (__m128i *)((char *)v30 - 1);
      v29 = (const __m128i *)((char *)v29 - 1);
      v30->m128i_i8[0] = v29->m128i_i8[0];
    }
    return a1;
  }
  else
  {
    if ( Size < 0x20 )
      goto CopyUpDwordMov_0;
    if ( Size < 0x80 )
    {
      if ( !_bittest(&dword_10033060, 1u) )
        goto Dword_align_0;
      goto XmmCopySmallTest_0;
    }
    if ( _bittest(&dword_10034D1C, 1u) )
    {
      qmemcpy(a1, Src, Size);
      return a1;
    }
    if ( (((unsigned int)Src ^ (unsigned int)a1) & 0xF) == 0 && _bittest(&dword_10033060, 1u) )
    {
      v45 = (unsigned __int8)Src & 0xF;
      if ( ((unsigned __int8)Src & 0xF) != 0 )
      {
        v63 = Size - (16 - v45);
        v60 = 16 - v45;
        v61 = v60 & 3;
        if ( (v60 & 3) != 0 )
        {
          do
          {
            v5->m128i_i8[0] = v3->m128i_i8[0];
            v3 = (const __m128i *)((char *)v3 + 1);
            v5 = (__m128i *)((char *)v5 + 1);
            --v61;
          }
          while ( v61 );
        }
        for ( i = v60 >> 2; i; --i )
        {
          v5->m128i_i32[0] = v3->m128i_i32[0];
          v3 = (const __m128i *)((char *)v3 + 4);
          v5 = (__m128i *)((char *)v5 + 4);
        }
        v4 = v63;
      }
      v46 = v4;
      v4 &= 0x7Fu;
      for ( j = v46 >> 7; j; --j )
      {
        si128 = _mm_load_si128(v3 + 1);
        v49 = _mm_load_si128(v3 + 2);
        v50 = _mm_load_si128(v3 + 3);
        *v5 = _mm_load_si128(v3);
        v5[1] = si128;
        v5[2] = v49;
        v5[3] = v50;
        v51 = _mm_load_si128(v3 + 5);
        v52 = _mm_load_si128(v3 + 6);
        v53 = _mm_load_si128(v3 + 7);
        v5[4] = _mm_load_si128(v3 + 4);
        v5[5] = v51;
        v5[6] = v52;
        v5[7] = v53;
        v3 += 8;
        v5 += 8;
      }
XmmCopySmallTest_0:
      if ( !v4 )
        return a1;
      for ( k = v4 >> 5; k; --k )
      {
        v55 = _mm_loadu_si128(v3 + 1);
        *v5 = _mm_loadu_si128(v3);
        v5[1] = v55;
        v3 += 2;
        v5 += 2;
      }
CopyUpDwordMov_0:
      v56 = v4 & 0x1F;
      if ( v56 )
      {
        v57 = v56;
        for ( m = v56 >> 2; m; --m )
        {
          v5->m128i_i32[0] = v3->m128i_i32[0];
          v5 = (__m128i *)((char *)v5 + 4);
          v3 = (const __m128i *)((char *)v3 + 4);
        }
        v59 = v57 & 3;
        if ( (v57 & 3) != 0 )
        {
          do
          {
            v5->m128i_i8[0] = v3->m128i_i8[0];
            v3 = (const __m128i *)((char *)v3 + 1);
            v5 = (__m128i *)((char *)v5 + 1);
            --v59;
          }
          while ( v59 );
        }
      }
      return a1;
    }
    if ( !_bittest(&dword_10034D1C, 0) || ((unsigned __int8)a1 & 3) != 0 )
    {
Dword_align_0:
      if ( ((unsigned __int8)a1 & 3) != 0 )
      {
        do
        {
          v5->m128i_i8[0] = v3->m128i_i8[0];
          --v4;
          v3 = (const __m128i *)((char *)v3 + 1);
          v5 = (__m128i *)((char *)v5 + 1);
        }
        while ( ((unsigned __int8)v5 & 3) != 0 );
      }
      goto Dword_align_Ok_0;
    }
    if ( ((unsigned __int8)Src & 3) != 0 )
    {
Dword_align_Ok_0:
      v27 = v4;
      if ( v4 >= 0x20 )
      {
        v28 = v4 >> 2;
        qmemcpy(v5, v3, 4 * v28);
        v13 = (const __m128i *)((char *)v3 + 4 * v28);
        v5 = (__m128i *)((char *)v5 + 4 * v28);
        switch ( v27 & 3 )
        {
          case 0:
            goto TrailingUp0_0;
          case 1:
            goto TrailingUp1_0;
          case 2:
            goto TrailingUp2_0;
          case 3:
            goto TrailingUp3_0;
        }
      }
      goto CopyUpDwordMov_0;
    }
    if ( ((unsigned __int8)a1 & 4) != 0 )
    {
      v4 = Size - 4;
      v3 = (const __m128i *)((char *)Src + 4);
      *(_DWORD *)a1 = *(_DWORD *)Src;
      v5 = (__m128i *)((char *)a1 + 4);
    }
    if ( ((unsigned __int8)v5 & 8) != 0 )
    {
      v7 = v3->m128i_i64[0];
      v4 -= 8;
      v3 = (const __m128i *)((char *)v3 + 8);
      v5->m128i_i64[0] = v7;
      v5 = (__m128i *)((char *)v5 + 8);
    }
    if ( ((unsigned __int8)v3 & 7) != 0 )
    {
      if ( ((unsigned __int8)v3 & 8) != 0 )
      {
        v8 = _mm_load_si128((const __m128i *)((char *)v3 - 12));
        v9 = (const __m128i *)((char *)v3 - 12);
        do
        {
          v10 = _mm_load_si128(v9 + 1);
          v4 -= 48;
          v11 = _mm_load_si128(v9 + 2);
          v12 = _mm_load_si128(v9 + 3);
          v9 += 3;
          *v5 = _mm_alignr_epi8(v10, v8, 12);
          v5[1] = _mm_alignr_epi8(v11, v10, 12);
          v8 = v12;
          v5[2] = _mm_alignr_epi8(v12, v11, 12);
          v5 += 3;
        }
        while ( v4 >= 0x30 );
        v13 = (const __m128i *)((char *)&v9->m128i_u64[1] + 4);
      }
      else
      {
        v19 = _mm_load_si128((const __m128i *)((char *)v3 - 4));
        v20 = (const __m128i *)((char *)v3 - 4);
        do
        {
          v21 = _mm_load_si128(v20 + 1);
          v4 -= 48;
          v22 = _mm_load_si128(v20 + 2);
          v23 = _mm_load_si128(v20 + 3);
          v20 += 3;
          *v5 = _mm_alignr_epi8(v21, v19, 4);
          v5[1] = _mm_alignr_epi8(v22, v21, 4);
          v19 = v23;
          v5[2] = _mm_alignr_epi8(v23, v22, 4);
          v5 += 3;
        }
        while ( v4 >= 0x30 );
        v13 = (const __m128i *)((char *)v20->m128i_i64 + 4);
      }
    }
    else
    {
      v14 = _mm_load_si128((const __m128i *)((char *)v3 - 8));
      v15 = (const __m128i *)((char *)v3 - 8);
      do
      {
        v16 = _mm_load_si128(v15 + 1);
        v4 -= 48;
        v17 = _mm_load_si128(v15 + 2);
        v18 = _mm_load_si128(v15 + 3);
        v15 += 3;
        *v5 = _mm_alignr_epi8(v16, v14, 8);
        v5[1] = _mm_alignr_epi8(v17, v16, 8);
        v14 = v18;
        v5[2] = _mm_alignr_epi8(v18, v17, 8);
        v5 += 3;
      }
      while ( v4 >= 0x30 );
      v13 = (const __m128i *)&v15->m128i_u64[1];
    }
    while ( v4 >= 0x10 )
    {
LABEL_30:
      v24 = _mm_loadu_si128(v13);
      v4 -= 16;
      ++v13;
      *v5++ = v24;
    }
    if ( (v4 & 4) != 0 )
    {
      v25 = v13->m128i_i32[0];
      v4 -= 4;
      v13 = (const __m128i *)((char *)v13 + 4);
      v5->m128i_i32[0] = v25;
      v5 = (__m128i *)((char *)v5 + 4);
    }
    if ( (v4 & 8) != 0 )
    {
      v26 = v13->m128i_i64[0];
      v4 -= 8;
      v13 = (const __m128i *)((char *)v13 + 8);
      v5->m128i_i64[0] = v26;
      v5 = (__m128i *)((char *)v5 + 8);
    }
    switch ( v4 )
    {
      case 0u:
TrailingUp0_0:
        result = a1;
        break;
      case 1u:
TrailingUp1_0:
        v5->m128i_i8[0] = v13->m128i_i8[0];
        result = a1;
        break;
      case 2u:
TrailingUp2_0:
        v5->m128i_i8[0] = v13->m128i_i8[0];
        v5->m128i_i8[1] = v13->m128i_i8[1];
        result = a1;
        break;
      case 3u:
TrailingUp3_0:
        v5->m128i_i8[0] = v13->m128i_i8[0];
        v5->m128i_i8[1] = v13->m128i_i8[1];
        v5->m128i_i8[2] = v13->m128i_i8[2];
        result = a1;
        break;
      default:
        goto LABEL_30;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10011cf0  push    edi
0x10011cf1  push    esi
0x10011cf2  mov     esi, [esp+8+Src]
0x10011cf6  mov     ecx, [esp+8+Size]
0x10011cfa  mov     edi, [esp+8+arg_0]
0x10011cfe  mov     eax, ecx
0x10011d00  mov     edx, ecx
0x10011d02  add     eax, esi
0x10011d04  cmp     edi, esi
0x10011d06  jbe     short CopyUp_0
0x10011d08  cmp     edi, eax
0x10011d0a  jb      CopyDown_0
0x10011d10  cmp     ecx, 20h ; ' '
0x10011d13  jb      CopyUpDwordMov_0
0x10011d19  cmp     ecx, 80h
0x10011d1f  jnb     short CopyUpLargeMov_0
0x10011d21  bt      dword_10033060, 1
0x10011d29  jb      XmmCopySmallTest_0
0x10011d2f  jmp     Dword_align_0
0x10011d34  bt      dword_10034D1C, 1
0x10011d3c  jnb     short CopyUpSSE2Check_0
0x10011d3e  rep movsb
0x10011d40  mov     eax, [esp+8+arg_0]
0x10011d44  pop     esi
0x10011d45  pop     edi
0x10011d46  retn
0x10011d47  mov     eax, edi
0x10011d49  xor     eax, esi
0x10011d4b  test    eax, 0Fh
0x10011d50  jnz     short AtomChk_0
0x10011d52  bt      dword_10033060, 1
0x10011d5a  jb      XmmCopy_0
0x10011d60  bt      dword_10034D1C, 0
0x10011d68  jnb     Dword_align_0
0x10011d6e  test    edi, 3
0x10011d74  jnz     Dword_align_0
0x10011d7a  test    esi, 3
0x10011d80  jnz     Dword_align_Ok_0
0x10011d86  bt      edi, 2
0x10011d8a  jnb     short PalignHead8_0
0x10011d8c  mov     eax, [esi]
0x10011d8e  sub     ecx, 4
0x10011d91  lea     esi, [esi+4]
0x10011d94  mov     [edi], eax
0x10011d96  lea     edi, [edi+4]
0x10011d99  bt      edi, 3
0x10011d9d  jnb     short PalignLoop_0
0x10011d9f  movq    xmm1, qword ptr [esi]
0x10011da3  sub     ecx, 8
0x10011da6  lea     esi, [esi+8]
0x10011da9  movq    qword ptr [edi], xmm1
0x10011dad  lea     edi, [edi+8]
0x10011db0  test    esi, 7
0x10011db6  jz      short MovPalign8_0
0x10011db8  bt      esi, 3
0x10011dbc  jnb     MovPalign4_0
0x10011dc2  movdqa  xmm1, xmmword ptr [esi-0Ch]
0x10011dc7  lea     esi, [esi-0Ch]
0x10011dca  mov     edi, edi
0x10011dcc  movdqa  xmm3, xmmword ptr [esi+10h]
0x10011dd1  sub     ecx, 30h ; '0'
0x10011dd4  movdqa  xmm0, xmmword ptr [esi+20h]
0x10011dd9  movdqa  xmm5, xmmword ptr [esi+30h]
0x10011dde  lea     esi, [esi+30h]
0x10011de1  cmp     ecx, 30h ; '0'
0x10011de4  movdqa  xmm2, xmm3
0x10011de8  palignr xmm3, xmm1, 0Ch
0x10011dee  movdqa  xmmword ptr [edi], xmm3
0x10011df2  movdqa  xmm4, xmm0
0x10011df6  palignr xmm0, xmm2, 0Ch
0x10011dfc  movdqa  xmmword ptr [edi+10h], xmm0
0x10011e01  movdqa  xmm1, xmm5
0x10011e05  palignr xmm5, xmm4, 0Ch
0x10011e0b  movdqa  xmmword ptr [edi+20h], xmm5
0x10011e10  lea     edi, [edi+30h]
0x10011e13  jnb     short PalignLoop12_0
0x10011e15  lea     esi, [esi+0Ch]
0x10011e18  jmp     PalignTail_0
0x10011e1d  movdqa  xmm1, xmmword ptr [esi-8]
0x10011e22  lea     esi, [esi-8]
0x10011e25  lea     ecx, [ecx+0]
0x10011e28  movdqa  xmm3, xmmword ptr [esi+10h]
0x10011e2d  sub     ecx, 30h ; '0'
0x10011e30  movdqa  xmm0, xmmword ptr [esi+20h]
0x10011e35  movdqa  xmm5, xmmword ptr [esi+30h]
0x10011e3a  lea     esi, [esi+30h]
0x10011e3d  cmp     ecx, 30h ; '0'
0x10011e40  movdqa  xmm2, xmm3
0x10011e44  palignr xmm3, xmm1, 8
0x10011e4a  movdqa  xmmword ptr [edi], xmm3
0x10011e4e  movdqa  xmm4, xmm0
0x10011e52  palignr xmm0, xmm2, 8
0x10011e58  movdqa  xmmword ptr [edi+10h], xmm0
0x10011e5d  movdqa  xmm1, xmm5
0x10011e61  palignr xmm5, xmm4, 8
0x10011e67  movdqa  xmmword ptr [edi+20h], xmm5
0x10011e6c  lea     edi, [edi+30h]
0x10011e6f  jnb     short PalignLoop8_0
0x10011e71  lea     esi, [esi+8]
0x10011e74  jmp     short PalignTail_0
0x10011e76  movdqa  xmm1, xmmword ptr [esi-4]
0x10011e7b  lea     esi, [esi-4]
0x10011e7e  mov     edi, edi
0x10011e80  movdqa  xmm3, xmmword ptr [esi+10h]
0x10011e85  sub     ecx, 30h ; '0'
0x10011e88  movdqa  xmm0, xmmword ptr [esi+20h]
0x10011e8d  movdqa  xmm5, xmmword ptr [esi+30h]
0x10011e92  lea     esi, [esi+30h]
0x10011e95  cmp     ecx, 30h ; '0'
0x10011e98  movdqa  xmm2, xmm3
0x10011e9c  palignr xmm3, xmm1, 4
0x10011ea2  movdqa  xmmword ptr [edi], xmm3
0x10011ea6  movdqa  xmm4, xmm0
0x10011eaa  palignr xmm0, xmm2, 4
0x10011eb0  movdqa  xmmword ptr [edi+10h], xmm0
0x10011eb5  movdqa  xmm1, xmm5
0x10011eb9  palignr xmm5, xmm4, 4
0x10011ebf  movdqa  xmmword ptr [edi+20h], xmm5
0x10011ec4  lea     edi, [edi+30h]
0x10011ec7  jnb     short PalignLoop4_0
0x10011ec9  lea     esi, [esi+4]
0x10011ecc  cmp     ecx, 10h
0x10011ecf  jb      short PalignTail4_0
0x10011ed1  movdqu  xmm1, xmmword ptr [esi]; jumptable 10011F15 default case
0x10011ed5  sub     ecx, 10h
0x10011ed8  lea     esi, [esi+10h]
0x10011edb  movdqa  xmmword ptr [edi], xmm1
0x10011edf  lea     edi, [edi+10h]
0x10011ee2  jmp     short PalignTail_0
0x10011ee4  bt      ecx, 2
0x10011ee8  jnb     short PalignTail8_0
0x10011eea  mov     eax, [esi]
0x10011eec  sub     ecx, 4
0x10011eef  lea     esi, [esi+4]
0x10011ef2  mov     [edi], eax
0x10011ef4  lea     edi, [edi+4]
0x10011ef7  bt      ecx, 3
0x10011efb  jnb     short PalignTailLE3_0
0x10011efd  movq    xmm1, qword ptr [esi]
0x10011f01  sub     ecx, 8
0x10011f04  lea     esi, [esi+8]
0x10011f07  movq    qword ptr [edi], xmm1
0x10011f0b  lea     edi, [edi+8]
0x10011f0e  mov     eax, ds:jpt_10011F15[ecx*4]; switch 4 cases
0x10011f15  jmp     eax; switch jump
0x10011f17  test    edi, 3
0x10011f1d  jz      short Dword_align_Ok_0
0x10011f1f  mov     al, [esi]
0x10011f21  mov     [edi], al
0x10011f23  dec     ecx
0x10011f24  add     esi, 1
0x10011f27  add     edi, 1
0x10011f2a  test    edi, 3
0x10011f30  jnz     short Dword_up_align_loop_0
0x10011f32  mov     edx, ecx
0x10011f34  cmp     ecx, 20h ; ' '
0x10011f37  jb      CopyUpDwordMov_0
0x10011f3d  shr     ecx, 2
0x10011f40  rep movsd
0x10011f42  and     edx, 3
0x10011f45  jmp     ds:jpt_10011F15[edx*4]; switch 4 cases
0x10011f4c  jmp     dword ptr ds:TrailingUp0_0[ecx*4]; jumptable 10011F15 case 0
0x10011f64  mov     eax, [esp+8+arg_0]; jumptable 10011F15 case 0
0x10011f68  pop     esi
0x10011f69  pop     edi
0x10011f6a  retn
0x10011f6c  mov     al, [esi]; jumptable 10011F15 case 1
0x10011f6e  mov     [edi], al
0x10011f70  mov     eax, [esp+8+arg_0]
0x10011f74  pop     esi
0x10011f75  pop     edi
0x10011f76  retn
0x10011f78  mov     al, [esi]; jumptable 10011F15 case 2
0x10011f7a  mov     [edi], al
0x10011f7c  mov     al, [esi+1]
0x10011f7f  mov     [edi+1], al
0x10011f82  mov     eax, [esp+8+arg_0]
0x10011f86  pop     esi
0x10011f87  pop     edi
0x10011f88  retn
0x10011f8c  mov     al, [esi]; jumptable 10011F15 case 3
0x10011f8e  mov     [edi], al
0x10011f90  mov     al, [esi+1]
0x10011f93  mov     [edi+1], al
0x10011f96  mov     al, [esi+2]
0x10011f99  mov     [edi+2], al
0x10011f9c  mov     eax, [esp+8+arg_0]
0x10011fa0  pop     esi
0x10011fa1  pop     edi
0x10011fa2  retn
0x10011fa4  lea     esi, [esi+ecx]
0x10011fa7  lea     edi, [edi+ecx]
0x10011faa  cmp     ecx, 20h ; ' '
0x10011fad  jb      CopyDownSmall_0
0x10011fb3  bt      dword_10033060, 1
0x10011fbb  jb      XmmMovLargeAlignTest_0
0x10011fc1  test    edi, 3
0x10011fc7  jz      short CopyDownAligned_0
0x10011fc9  mov     edx, edi
0x10011fcb  and     edx, 3
0x10011fce  sub     ecx, edx
0x10011fd0  mov     al, [esi-1]
0x10011fd3  mov     [edi-1], al
0x10011fd6  dec     esi
0x10011fd7  dec     edi
0x10011fd8  sub     edx, 1
0x10011fdb  jnz     short CopyDownAlignLoop_0
0x10011fdd  cmp     ecx, 20h ; ' '
0x10011fe0  jb      CopyDownSmall_0
0x10011fe6  mov     edx, ecx
0x10011fe8  shr     ecx, 2
0x10011feb  and     edx, 3
0x10011fee  sub     esi, 4
0x10011ff1  sub     edi, 4
0x10011ff4  std
0x10011ff5  rep movsd
0x10011ff7  cld
0x10011ff8  jmp     ds:jpt_10011FF8[edx*4]; switch 4 cases
0x10012010  mov     eax, [esp+8+arg_0]; jumptable 10011FF8 case 0
0x10012014  pop     esi
0x10012015  pop     edi
0x10012016  retn
0x10012018  mov     al, [esi+3]; jumptable 10011FF8 case 1
0x1001201b  mov     [edi+3], al
0x1001201e  mov     eax, [esp+8+arg_0]
0x10012022  pop     esi
0x10012023  pop     edi
0x10012024  retn
0x10012028  mov     al, [esi+3]; jumptable 10011FF8 case 2
0x1001202b  mov     [edi+3], al
0x1001202e  mov     al, [esi+2]
0x10012031  mov     [edi+2], al
0x10012034  mov     eax, [esp+8+arg_0]
0x10012038  pop     esi
0x10012039  pop     edi
0x1001203a  retn
0x1001203c  mov     al, [esi+3]; jumptable 10011FF8 case 3
0x1001203f  mov     [edi+3], al
0x10012042  mov     al, [esi+2]
0x10012045  mov     [edi+2], al
0x10012048  mov     al, [esi+1]
0x1001204b  mov     [edi+1], al
0x1001204e  mov     eax, [esp+8+arg_0]
0x10012052  pop     esi
0x10012053  pop     edi
0x10012054  retn
0x10012055  test    edi, 0Fh
0x1001205b  jz      short XmmMovLargeLoop_0
0x1001205d  dec     ecx
0x1001205e  dec     esi
0x1001205f  dec     edi
0x10012060  mov     al, [esi]
0x10012062  mov     [edi], al
0x10012064  test    edi, 0Fh
0x1001206a  jnz     short XmmMovAlignLoop_0
0x1001206c  cmp     ecx, 80h
0x10012072  jb      short XmmMovSmallTest_0
0x10012074  sub     esi, 80h
0x1001207a  sub     edi, 80h
0x10012080  movdqu  xmm0, xmmword ptr [esi]
0x10012084  movdqu  xmm1, xmmword ptr [esi+10h]
0x10012089  movdqu  xmm2, xmmword ptr [esi+20h]
0x1001208e  movdqu  xmm3, xmmword ptr [esi+30h]
0x10012093  movdqu  xmm4, xmmword ptr [esi+40h]
0x10012098  movdqu  xmm5, xmmword ptr [esi+50h]
0x1001209d  movdqu  xmm6, xmmword ptr [esi+60h]
0x100120a2  movdqu  xmm7, xmmword ptr [esi+70h]
0x100120a7  movdqu  xmmword ptr [edi], xmm0
0x100120ab  movdqu  xmmword ptr [edi+10h], xmm1
0x100120b0  movdqu  xmmword ptr [edi+20h], xmm2
0x100120b5  movdqu  xmmword ptr [edi+30h], xmm3
0x100120ba  movdqu  xmmword ptr [edi+40h], xmm4
0x100120bf  movdqu  xmmword ptr [edi+50h], xmm5
0x100120c4  movdqu  xmmword ptr [edi+60h], xmm6
0x100120c9  movdqu  xmmword ptr [edi+70h], xmm7
0x100120ce  sub     ecx, 80h
0x100120d4  test    ecx, 0FFFFFF80h
0x100120da  jnz     short XmmMovLargeLoop_0
0x100120dc  cmp     ecx, 20h ; ' '
0x100120df  jb      short CopyDownSmall_0
0x100120e1  sub     esi, 20h ; ' '
0x100120e4  sub     edi, 20h ; ' '
0x100120e7  movdqu  xmm0, xmmword ptr [esi]
0x100120eb  movdqu  xmm1, xmmword ptr [esi+10h]
0x100120f0  movdqu  xmmword ptr [edi], xmm0
0x100120f4  movdqu  xmmword ptr [edi+10h], xmm1
0x100120f9  sub     ecx, 20h ; ' '
0x100120fc  test    ecx, 0FFFFFFE0h
0x10012102  jnz     short XmmMovSmallLoop_0
0x10012104  test    ecx, 0FFFFFFFCh
0x1001210a  jz      short CopyDownByteTest_0
0x1001210c  sub     edi, 4
0x1001210f  sub     esi, 4
0x10012112  mov     eax, [esi]
0x10012114  mov     [edi], eax
0x10012116  sub     ecx, 4
0x10012119  test    ecx, 0FFFFFFFCh
0x1001211f  jnz     short CopyDownDwordLoop_0
0x10012121  test    ecx, ecx
0x10012123  jz      short CopyDownReturn_0
  ... truncated ...
```
