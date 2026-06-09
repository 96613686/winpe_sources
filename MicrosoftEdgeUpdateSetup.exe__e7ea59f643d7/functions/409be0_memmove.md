# _memmove

- ea: `0x409be0`
- end: `0x40a154`
- name: `_memmove`
- size: `1396`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x40111b`
- `0x4039b7`
- `0x403c95`
- `0x403e90`
- `0x4045bf`
- `0x404d09`
- `0x40539c`
- `0x4061f3`
- `0x407a3f`
- `0x407cd8`
- `0x40a154`
- `0x40da5c`
- `0x40fece`
- `0x412ad9`
- `0x412f09`
- `0x413e05`
- `0x414da1`
- `0x415318`
- `0x41b167`
- `0x41b6bb`

## callees

- `0x409be0`

## pseudocode

```c
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
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
      if ( _bittest(&dword_426010, 1u) )
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
      goto CopyUpDwordMov;
    if ( Size < 0x80 )
    {
      if ( !_bittest(&dword_426010, 1u) )
        goto Dword_align;
      goto XmmCopySmallTest;
    }
    if ( _bittest(&dword_426968, 1u) )
    {
      qmemcpy(a1, Src, Size);
      return a1;
    }
    if ( (((unsigned int)Src ^ (unsigned int)a1) & 0xF) == 0 && _bittest(&dword_426010, 1u) )
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
XmmCopySmallTest:
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
CopyUpDwordMov:
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
    if ( !_bittest(&dword_426968, 0) || ((unsigned __int8)a1 & 3) != 0 )
    {
Dword_align:
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
      goto Dword_align_Ok;
    }
    if ( ((unsigned __int8)Src & 3) != 0 )
    {
Dword_align_Ok:
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
            goto TrailingUp0;
          case 1:
            goto TrailingUp1;
          case 2:
            goto TrailingUp2;
          case 3:
            goto TrailingUp3;
        }
      }
      goto CopyUpDwordMov;
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
TrailingUp0:
        result = a1;
        break;
      case 1u:
TrailingUp1:
        v5->m128i_i8[0] = v13->m128i_i8[0];
        result = a1;
        break;
      case 2u:
TrailingUp2:
        v5->m128i_i8[0] = v13->m128i_i8[0];
        v5->m128i_i8[1] = v13->m128i_i8[1];
        result = a1;
        break;
      case 3u:
TrailingUp3:
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
0x409be0  push    edi
0x409be1  push    esi
0x409be2  mov     esi, [esp+8+Src]
0x409be6  mov     ecx, [esp+8+Size]
0x409bea  mov     edi, [esp+8+arg_0]
0x409bee  mov     eax, ecx
0x409bf0  mov     edx, ecx
0x409bf2  add     eax, esi
0x409bf4  cmp     edi, esi
0x409bf6  jbe     short CopyUp
0x409bf8  cmp     edi, eax
0x409bfa  jb      CopyDown
0x409c00  cmp     ecx, 20h ; ' '
0x409c03  jb      CopyUpDwordMov
0x409c09  cmp     ecx, 80h
0x409c0f  jnb     short CopyUpLargeMov
0x409c11  bt      dword_426010, 1
0x409c19  jb      XmmCopySmallTest
0x409c1f  jmp     Dword_align
0x409c24  bt      dword_426968, 1
0x409c2c  jnb     short CopyUpSSE2Check
0x409c2e  rep movsb
0x409c30  mov     eax, [esp+8+arg_0]
0x409c34  pop     esi
0x409c35  pop     edi
0x409c36  retn
0x409c37  mov     eax, edi
0x409c39  xor     eax, esi
0x409c3b  test    eax, 0Fh
0x409c40  jnz     short AtomChk
0x409c42  bt      dword_426010, 1
0x409c4a  jb      XmmCopy
0x409c50  bt      dword_426968, 0
0x409c58  jnb     Dword_align
0x409c5e  test    edi, 3
0x409c64  jnz     Dword_align
0x409c6a  test    esi, 3
0x409c70  jnz     Dword_align_Ok
0x409c76  bt      edi, 2
0x409c7a  jnb     short PalignHead8
0x409c7c  mov     eax, [esi]
0x409c7e  sub     ecx, 4
0x409c81  lea     esi, [esi+4]
0x409c84  mov     [edi], eax
0x409c86  lea     edi, [edi+4]
0x409c89  bt      edi, 3
0x409c8d  jnb     short PalignLoop
0x409c8f  movq    xmm1, qword ptr [esi]
0x409c93  sub     ecx, 8
0x409c96  lea     esi, [esi+8]
0x409c99  movq    qword ptr [edi], xmm1
0x409c9d  lea     edi, [edi+8]
0x409ca0  test    esi, 7
0x409ca6  jz      short MovPalign8
0x409ca8  bt      esi, 3
0x409cac  jnb     MovPalign4
0x409cb2  movdqa  xmm1, xmmword ptr [esi-0Ch]
0x409cb7  lea     esi, [esi-0Ch]
0x409cba  mov     edi, edi
0x409cbc  movdqa  xmm3, xmmword ptr [esi+10h]
0x409cc1  sub     ecx, 30h ; '0'
0x409cc4  movdqa  xmm0, xmmword ptr [esi+20h]
0x409cc9  movdqa  xmm5, xmmword ptr [esi+30h]
0x409cce  lea     esi, [esi+30h]
0x409cd1  cmp     ecx, 30h ; '0'
0x409cd4  movdqa  xmm2, xmm3
0x409cd8  palignr xmm3, xmm1, 0Ch
0x409cde  movdqa  xmmword ptr [edi], xmm3
0x409ce2  movdqa  xmm4, xmm0
0x409ce6  palignr xmm0, xmm2, 0Ch
0x409cec  movdqa  xmmword ptr [edi+10h], xmm0
0x409cf1  movdqa  xmm1, xmm5
0x409cf5  palignr xmm5, xmm4, 0Ch
0x409cfb  movdqa  xmmword ptr [edi+20h], xmm5
0x409d00  lea     edi, [edi+30h]
0x409d03  jnb     short PalignLoop12
0x409d05  lea     esi, [esi+0Ch]
0x409d08  jmp     PalignTail
0x409d0d  movdqa  xmm1, xmmword ptr [esi-8]
0x409d12  lea     esi, [esi-8]
0x409d15  lea     ecx, [ecx+0]
0x409d18  movdqa  xmm3, xmmword ptr [esi+10h]
0x409d1d  sub     ecx, 30h ; '0'
0x409d20  movdqa  xmm0, xmmword ptr [esi+20h]
0x409d25  movdqa  xmm5, xmmword ptr [esi+30h]
0x409d2a  lea     esi, [esi+30h]
0x409d2d  cmp     ecx, 30h ; '0'
0x409d30  movdqa  xmm2, xmm3
0x409d34  palignr xmm3, xmm1, 8
0x409d3a  movdqa  xmmword ptr [edi], xmm3
0x409d3e  movdqa  xmm4, xmm0
0x409d42  palignr xmm0, xmm2, 8
0x409d48  movdqa  xmmword ptr [edi+10h], xmm0
0x409d4d  movdqa  xmm1, xmm5
0x409d51  palignr xmm5, xmm4, 8
0x409d57  movdqa  xmmword ptr [edi+20h], xmm5
0x409d5c  lea     edi, [edi+30h]
0x409d5f  jnb     short PalignLoop8
0x409d61  lea     esi, [esi+8]
0x409d64  jmp     short PalignTail
0x409d66  movdqa  xmm1, xmmword ptr [esi-4]
0x409d6b  lea     esi, [esi-4]
0x409d6e  mov     edi, edi
0x409d70  movdqa  xmm3, xmmword ptr [esi+10h]
0x409d75  sub     ecx, 30h ; '0'
0x409d78  movdqa  xmm0, xmmword ptr [esi+20h]
0x409d7d  movdqa  xmm5, xmmword ptr [esi+30h]
0x409d82  lea     esi, [esi+30h]
0x409d85  cmp     ecx, 30h ; '0'
0x409d88  movdqa  xmm2, xmm3
0x409d8c  palignr xmm3, xmm1, 4
0x409d92  movdqa  xmmword ptr [edi], xmm3
0x409d96  movdqa  xmm4, xmm0
0x409d9a  palignr xmm0, xmm2, 4
0x409da0  movdqa  xmmword ptr [edi+10h], xmm0
0x409da5  movdqa  xmm1, xmm5
0x409da9  palignr xmm5, xmm4, 4
0x409daf  movdqa  xmmword ptr [edi+20h], xmm5
0x409db4  lea     edi, [edi+30h]
0x409db7  jnb     short PalignLoop4
0x409db9  lea     esi, [esi+4]
0x409dbc  cmp     ecx, 10h
0x409dbf  jb      short PalignTail4
0x409dc1  movdqu  xmm1, xmmword ptr [esi]; jumptable 00409E05 default case
0x409dc5  sub     ecx, 10h
0x409dc8  lea     esi, [esi+10h]
0x409dcb  movdqa  xmmword ptr [edi], xmm1
0x409dcf  lea     edi, [edi+10h]
0x409dd2  jmp     short PalignTail
0x409dd4  bt      ecx, 2
0x409dd8  jnb     short PalignTail8
0x409dda  mov     eax, [esi]
0x409ddc  sub     ecx, 4
0x409ddf  lea     esi, [esi+4]
0x409de2  mov     [edi], eax
0x409de4  lea     edi, [edi+4]
0x409de7  bt      ecx, 3
0x409deb  jnb     short PalignTailLE3
0x409ded  movq    xmm1, qword ptr [esi]
0x409df1  sub     ecx, 8
0x409df4  lea     esi, [esi+8]
0x409df7  movq    qword ptr [edi], xmm1
0x409dfb  lea     edi, [edi+8]
0x409dfe  mov     eax, ds:jpt_409E05[ecx*4]; switch 4 cases
0x409e05  jmp     eax; switch jump
0x409e07  test    edi, 3
0x409e0d  jz      short Dword_align_Ok
0x409e0f  mov     al, [esi]
0x409e11  mov     [edi], al
0x409e13  dec     ecx
0x409e14  add     esi, 1
0x409e17  add     edi, 1
0x409e1a  test    edi, 3
0x409e20  jnz     short Dword_up_align_loop
0x409e22  mov     edx, ecx
0x409e24  cmp     ecx, 20h ; ' '
0x409e27  jb      CopyUpDwordMov
0x409e2d  shr     ecx, 2
0x409e30  rep movsd
0x409e32  and     edx, 3
0x409e35  jmp     ds:jpt_409E05[edx*4]; switch 4 cases
0x409e3c  jmp     dword ptr ds:TrailingUp0[ecx*4]; jumptable 00409E05 case 0
0x409e54  mov     eax, [esp+8+arg_0]; jumptable 00409E05 case 0
0x409e58  pop     esi
0x409e59  pop     edi
0x409e5a  retn
0x409e5c  mov     al, [esi]; jumptable 00409E05 case 1
0x409e5e  mov     [edi], al
0x409e60  mov     eax, [esp+8+arg_0]
0x409e64  pop     esi
0x409e65  pop     edi
0x409e66  retn
0x409e68  mov     al, [esi]; jumptable 00409E05 case 2
0x409e6a  mov     [edi], al
0x409e6c  mov     al, [esi+1]
0x409e6f  mov     [edi+1], al
0x409e72  mov     eax, [esp+8+arg_0]
0x409e76  pop     esi
0x409e77  pop     edi
0x409e78  retn
0x409e7c  mov     al, [esi]; jumptable 00409E05 case 3
0x409e7e  mov     [edi], al
0x409e80  mov     al, [esi+1]
0x409e83  mov     [edi+1], al
0x409e86  mov     al, [esi+2]
0x409e89  mov     [edi+2], al
0x409e8c  mov     eax, [esp+8+arg_0]
0x409e90  pop     esi
0x409e91  pop     edi
0x409e92  retn
0x409e94  lea     esi, [esi+ecx]
0x409e97  lea     edi, [edi+ecx]
0x409e9a  cmp     ecx, 20h ; ' '
0x409e9d  jb      CopyDownSmall
0x409ea3  bt      dword_426010, 1
0x409eab  jb      XmmMovLargeAlignTest
0x409eb1  test    edi, 3
0x409eb7  jz      short CopyDownAligned
0x409eb9  mov     edx, edi
0x409ebb  and     edx, 3
0x409ebe  sub     ecx, edx
0x409ec0  mov     al, [esi-1]
0x409ec3  mov     [edi-1], al
0x409ec6  dec     esi
0x409ec7  dec     edi
0x409ec8  sub     edx, 1
0x409ecb  jnz     short CopyDownAlignLoop
0x409ecd  cmp     ecx, 20h ; ' '
0x409ed0  jb      CopyDownSmall
0x409ed6  mov     edx, ecx
0x409ed8  shr     ecx, 2
0x409edb  and     edx, 3
0x409ede  sub     esi, 4
0x409ee1  sub     edi, 4
0x409ee4  std
0x409ee5  rep movsd
0x409ee7  cld
0x409ee8  jmp     ds:jpt_409EE8[edx*4]; switch 4 cases
0x409f00  mov     eax, [esp+8+arg_0]; jumptable 00409EE8 case 0
0x409f04  pop     esi
0x409f05  pop     edi
0x409f06  retn
0x409f08  mov     al, [esi+3]; jumptable 00409EE8 case 1
0x409f0b  mov     [edi+3], al
0x409f0e  mov     eax, [esp+8+arg_0]
0x409f12  pop     esi
0x409f13  pop     edi
0x409f14  retn
0x409f18  mov     al, [esi+3]; jumptable 00409EE8 case 2
0x409f1b  mov     [edi+3], al
0x409f1e  mov     al, [esi+2]
0x409f21  mov     [edi+2], al
0x409f24  mov     eax, [esp+8+arg_0]
0x409f28  pop     esi
0x409f29  pop     edi
0x409f2a  retn
0x409f2c  mov     al, [esi+3]; jumptable 00409EE8 case 3
0x409f2f  mov     [edi+3], al
0x409f32  mov     al, [esi+2]
0x409f35  mov     [edi+2], al
0x409f38  mov     al, [esi+1]
0x409f3b  mov     [edi+1], al
0x409f3e  mov     eax, [esp+8+arg_0]
0x409f42  pop     esi
0x409f43  pop     edi
0x409f44  retn
0x409f45  test    edi, 0Fh
0x409f4b  jz      short XmmMovLargeLoop
0x409f4d  dec     ecx
0x409f4e  dec     esi
0x409f4f  dec     edi
0x409f50  mov     al, [esi]
0x409f52  mov     [edi], al
0x409f54  test    edi, 0Fh
0x409f5a  jnz     short XmmMovAlignLoop
0x409f5c  cmp     ecx, 80h
0x409f62  jb      short XmmMovSmallTest
0x409f64  sub     esi, 80h
0x409f6a  sub     edi, 80h
0x409f70  movdqu  xmm0, xmmword ptr [esi]
0x409f74  movdqu  xmm1, xmmword ptr [esi+10h]
0x409f79  movdqu  xmm2, xmmword ptr [esi+20h]
0x409f7e  movdqu  xmm3, xmmword ptr [esi+30h]
0x409f83  movdqu  xmm4, xmmword ptr [esi+40h]
0x409f88  movdqu  xmm5, xmmword ptr [esi+50h]
0x409f8d  movdqu  xmm6, xmmword ptr [esi+60h]
0x409f92  movdqu  xmm7, xmmword ptr [esi+70h]
0x409f97  movdqu  xmmword ptr [edi], xmm0
0x409f9b  movdqu  xmmword ptr [edi+10h], xmm1
0x409fa0  movdqu  xmmword ptr [edi+20h], xmm2
0x409fa5  movdqu  xmmword ptr [edi+30h], xmm3
0x409faa  movdqu  xmmword ptr [edi+40h], xmm4
0x409faf  movdqu  xmmword ptr [edi+50h], xmm5
0x409fb4  movdqu  xmmword ptr [edi+60h], xmm6
0x409fb9  movdqu  xmmword ptr [edi+70h], xmm7
0x409fbe  sub     ecx, 80h
0x409fc4  test    ecx, 0FFFFFF80h
0x409fca  jnz     short XmmMovLargeLoop
0x409fcc  cmp     ecx, 20h ; ' '
0x409fcf  jb      short CopyDownSmall
0x409fd1  sub     esi, 20h ; ' '
0x409fd4  sub     edi, 20h ; ' '
0x409fd7  movdqu  xmm0, xmmword ptr [esi]
0x409fdb  movdqu  xmm1, xmmword ptr [esi+10h]
0x409fe0  movdqu  xmmword ptr [edi], xmm0
0x409fe4  movdqu  xmmword ptr [edi+10h], xmm1
0x409fe9  sub     ecx, 20h ; ' '
0x409fec  test    ecx, 0FFFFFFE0h
0x409ff2  jnz     short XmmMovSmallLoop
0x409ff4  test    ecx, 0FFFFFFFCh
0x409ffa  jz      short CopyDownByteTest
0x409ffc  sub     edi, 4
0x409fff  sub     esi, 4
0x40a002  mov     eax, [esi]
0x40a004  mov     [edi], eax
0x40a006  sub     ecx, 4
0x40a009  test    ecx, 0FFFFFFFCh
0x40a00f  jnz     short CopyDownDwordLoop
0x40a011  test    ecx, ecx
0x40a013  jz      short CopyDownReturn
  ... truncated ...
```
