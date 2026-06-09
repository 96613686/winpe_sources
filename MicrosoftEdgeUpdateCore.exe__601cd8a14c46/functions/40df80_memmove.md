# _memmove

- ea: `0x40df80`
- end: `0x40e4f4`
- name: `_memmove`
- size: `1396`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x401ef9`
- `0x402110`
- `0x4023c6`
- `0x4034e9`
- `0x4059df`
- `0x4074f9`
- `0x409593`
- `0x409695`
- `0x40f240`
- `0x412edc`
- `0x414b0e`
- `0x414d77`
- `0x4177ad`
- `0x417bdd`
- `0x4187ca`
- `0x4196ff`
- `0x419c78`
- `0x41fa50`

## callees

- `0x40df80`

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
      if ( _bittest(&dword_43D010, 1u) )
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
      if ( !_bittest(&dword_43D010, 1u) )
        goto Dword_align;
      goto XmmCopySmallTest;
    }
    if ( _bittest(&dword_43E010, 1u) )
    {
      qmemcpy(a1, Src, Size);
      return a1;
    }
    if ( (((unsigned int)Src ^ (unsigned int)a1) & 0xF) == 0 && _bittest(&dword_43D010, 1u) )
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
    if ( !_bittest(&dword_43E010, 0) || ((unsigned __int8)a1 & 3) != 0 )
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
0x40df80  push    edi
0x40df81  push    esi
0x40df82  mov     esi, [esp+8+Src]
0x40df86  mov     ecx, [esp+8+Size]
0x40df8a  mov     edi, [esp+8+arg_0]
0x40df8e  mov     eax, ecx
0x40df90  mov     edx, ecx
0x40df92  add     eax, esi
0x40df94  cmp     edi, esi
0x40df96  jbe     short CopyUp
0x40df98  cmp     edi, eax
0x40df9a  jb      CopyDown
0x40dfa0  cmp     ecx, 20h ; ' '
0x40dfa3  jb      CopyUpDwordMov
0x40dfa9  cmp     ecx, 80h
0x40dfaf  jnb     short CopyUpLargeMov
0x40dfb1  bt      dword_43D010, 1
0x40dfb9  jb      XmmCopySmallTest
0x40dfbf  jmp     Dword_align
0x40dfc4  bt      dword_43E010, 1
0x40dfcc  jnb     short CopyUpSSE2Check
0x40dfce  rep movsb
0x40dfd0  mov     eax, [esp+8+arg_0]
0x40dfd4  pop     esi
0x40dfd5  pop     edi
0x40dfd6  retn
0x40dfd7  mov     eax, edi
0x40dfd9  xor     eax, esi
0x40dfdb  test    eax, 0Fh
0x40dfe0  jnz     short AtomChk
0x40dfe2  bt      dword_43D010, 1
0x40dfea  jb      XmmCopy
0x40dff0  bt      dword_43E010, 0
0x40dff8  jnb     Dword_align
0x40dffe  test    edi, 3
0x40e004  jnz     Dword_align
0x40e00a  test    esi, 3
0x40e010  jnz     Dword_align_Ok
0x40e016  bt      edi, 2
0x40e01a  jnb     short PalignHead8
0x40e01c  mov     eax, [esi]
0x40e01e  sub     ecx, 4
0x40e021  lea     esi, [esi+4]
0x40e024  mov     [edi], eax
0x40e026  lea     edi, [edi+4]
0x40e029  bt      edi, 3
0x40e02d  jnb     short PalignLoop
0x40e02f  movq    xmm1, qword ptr [esi]
0x40e033  sub     ecx, 8
0x40e036  lea     esi, [esi+8]
0x40e039  movq    qword ptr [edi], xmm1
0x40e03d  lea     edi, [edi+8]
0x40e040  test    esi, 7
0x40e046  jz      short MovPalign8
0x40e048  bt      esi, 3
0x40e04c  jnb     MovPalign4
0x40e052  movdqa  xmm1, xmmword ptr [esi-0Ch]
0x40e057  lea     esi, [esi-0Ch]
0x40e05a  mov     edi, edi
0x40e05c  movdqa  xmm3, xmmword ptr [esi+10h]
0x40e061  sub     ecx, 30h ; '0'
0x40e064  movdqa  xmm0, xmmword ptr [esi+20h]
0x40e069  movdqa  xmm5, xmmword ptr [esi+30h]
0x40e06e  lea     esi, [esi+30h]
0x40e071  cmp     ecx, 30h ; '0'
0x40e074  movdqa  xmm2, xmm3
0x40e078  palignr xmm3, xmm1, 0Ch
0x40e07e  movdqa  xmmword ptr [edi], xmm3
0x40e082  movdqa  xmm4, xmm0
0x40e086  palignr xmm0, xmm2, 0Ch
0x40e08c  movdqa  xmmword ptr [edi+10h], xmm0
0x40e091  movdqa  xmm1, xmm5
0x40e095  palignr xmm5, xmm4, 0Ch
0x40e09b  movdqa  xmmword ptr [edi+20h], xmm5
0x40e0a0  lea     edi, [edi+30h]
0x40e0a3  jnb     short PalignLoop12
0x40e0a5  lea     esi, [esi+0Ch]
0x40e0a8  jmp     PalignTail
0x40e0ad  movdqa  xmm1, xmmword ptr [esi-8]
0x40e0b2  lea     esi, [esi-8]
0x40e0b5  lea     ecx, [ecx+0]
0x40e0b8  movdqa  xmm3, xmmword ptr [esi+10h]
0x40e0bd  sub     ecx, 30h ; '0'
0x40e0c0  movdqa  xmm0, xmmword ptr [esi+20h]
0x40e0c5  movdqa  xmm5, xmmword ptr [esi+30h]
0x40e0ca  lea     esi, [esi+30h]
0x40e0cd  cmp     ecx, 30h ; '0'
0x40e0d0  movdqa  xmm2, xmm3
0x40e0d4  palignr xmm3, xmm1, 8
0x40e0da  movdqa  xmmword ptr [edi], xmm3
0x40e0de  movdqa  xmm4, xmm0
0x40e0e2  palignr xmm0, xmm2, 8
0x40e0e8  movdqa  xmmword ptr [edi+10h], xmm0
0x40e0ed  movdqa  xmm1, xmm5
0x40e0f1  palignr xmm5, xmm4, 8
0x40e0f7  movdqa  xmmword ptr [edi+20h], xmm5
0x40e0fc  lea     edi, [edi+30h]
0x40e0ff  jnb     short PalignLoop8
0x40e101  lea     esi, [esi+8]
0x40e104  jmp     short PalignTail
0x40e106  movdqa  xmm1, xmmword ptr [esi-4]
0x40e10b  lea     esi, [esi-4]
0x40e10e  mov     edi, edi
0x40e110  movdqa  xmm3, xmmword ptr [esi+10h]
0x40e115  sub     ecx, 30h ; '0'
0x40e118  movdqa  xmm0, xmmword ptr [esi+20h]
0x40e11d  movdqa  xmm5, xmmword ptr [esi+30h]
0x40e122  lea     esi, [esi+30h]
0x40e125  cmp     ecx, 30h ; '0'
0x40e128  movdqa  xmm2, xmm3
0x40e12c  palignr xmm3, xmm1, 4
0x40e132  movdqa  xmmword ptr [edi], xmm3
0x40e136  movdqa  xmm4, xmm0
0x40e13a  palignr xmm0, xmm2, 4
0x40e140  movdqa  xmmword ptr [edi+10h], xmm0
0x40e145  movdqa  xmm1, xmm5
0x40e149  palignr xmm5, xmm4, 4
0x40e14f  movdqa  xmmword ptr [edi+20h], xmm5
0x40e154  lea     edi, [edi+30h]
0x40e157  jnb     short PalignLoop4
0x40e159  lea     esi, [esi+4]
0x40e15c  cmp     ecx, 10h
0x40e15f  jb      short PalignTail4
0x40e161  movdqu  xmm1, xmmword ptr [esi]; jumptable 0040E1A5 default case
0x40e165  sub     ecx, 10h
0x40e168  lea     esi, [esi+10h]
0x40e16b  movdqa  xmmword ptr [edi], xmm1
0x40e16f  lea     edi, [edi+10h]
0x40e172  jmp     short PalignTail
0x40e174  bt      ecx, 2
0x40e178  jnb     short PalignTail8
0x40e17a  mov     eax, [esi]
0x40e17c  sub     ecx, 4
0x40e17f  lea     esi, [esi+4]
0x40e182  mov     [edi], eax
0x40e184  lea     edi, [edi+4]
0x40e187  bt      ecx, 3
0x40e18b  jnb     short PalignTailLE3
0x40e18d  movq    xmm1, qword ptr [esi]
0x40e191  sub     ecx, 8
0x40e194  lea     esi, [esi+8]
0x40e197  movq    qword ptr [edi], xmm1
0x40e19b  lea     edi, [edi+8]
0x40e19e  mov     eax, ds:jpt_40E1A5[ecx*4]; switch 4 cases
0x40e1a5  jmp     eax; switch jump
0x40e1a7  test    edi, 3
0x40e1ad  jz      short Dword_align_Ok
0x40e1af  mov     al, [esi]
0x40e1b1  mov     [edi], al
0x40e1b3  dec     ecx
0x40e1b4  add     esi, 1
0x40e1b7  add     edi, 1
0x40e1ba  test    edi, 3
0x40e1c0  jnz     short Dword_up_align_loop
0x40e1c2  mov     edx, ecx
0x40e1c4  cmp     ecx, 20h ; ' '
0x40e1c7  jb      CopyUpDwordMov
0x40e1cd  shr     ecx, 2
0x40e1d0  rep movsd
0x40e1d2  and     edx, 3
0x40e1d5  jmp     ds:jpt_40E1A5[edx*4]; switch 4 cases
0x40e1dc  jmp     dword ptr ds:TrailingUp0[ecx*4]; jumptable 0040E1A5 case 0
0x40e1f4  mov     eax, [esp+8+arg_0]; jumptable 0040E1A5 case 0
0x40e1f8  pop     esi
0x40e1f9  pop     edi
0x40e1fa  retn
0x40e1fc  mov     al, [esi]; jumptable 0040E1A5 case 1
0x40e1fe  mov     [edi], al
0x40e200  mov     eax, [esp+8+arg_0]
0x40e204  pop     esi
0x40e205  pop     edi
0x40e206  retn
0x40e208  mov     al, [esi]; jumptable 0040E1A5 case 2
0x40e20a  mov     [edi], al
0x40e20c  mov     al, [esi+1]
0x40e20f  mov     [edi+1], al
0x40e212  mov     eax, [esp+8+arg_0]
0x40e216  pop     esi
0x40e217  pop     edi
0x40e218  retn
0x40e21c  mov     al, [esi]; jumptable 0040E1A5 case 3
0x40e21e  mov     [edi], al
0x40e220  mov     al, [esi+1]
0x40e223  mov     [edi+1], al
0x40e226  mov     al, [esi+2]
0x40e229  mov     [edi+2], al
0x40e22c  mov     eax, [esp+8+arg_0]
0x40e230  pop     esi
0x40e231  pop     edi
0x40e232  retn
0x40e234  lea     esi, [esi+ecx]
0x40e237  lea     edi, [edi+ecx]
0x40e23a  cmp     ecx, 20h ; ' '
0x40e23d  jb      CopyDownSmall
0x40e243  bt      dword_43D010, 1
0x40e24b  jb      XmmMovLargeAlignTest
0x40e251  test    edi, 3
0x40e257  jz      short CopyDownAligned
0x40e259  mov     edx, edi
0x40e25b  and     edx, 3
0x40e25e  sub     ecx, edx
0x40e260  mov     al, [esi-1]
0x40e263  mov     [edi-1], al
0x40e266  dec     esi
0x40e267  dec     edi
0x40e268  sub     edx, 1
0x40e26b  jnz     short CopyDownAlignLoop
0x40e26d  cmp     ecx, 20h ; ' '
0x40e270  jb      CopyDownSmall
0x40e276  mov     edx, ecx
0x40e278  shr     ecx, 2
0x40e27b  and     edx, 3
0x40e27e  sub     esi, 4
0x40e281  sub     edi, 4
0x40e284  std
0x40e285  rep movsd
0x40e287  cld
0x40e288  jmp     ds:jpt_40E288[edx*4]; switch 4 cases
0x40e2a0  mov     eax, [esp+8+arg_0]; jumptable 0040E288 case 0
0x40e2a4  pop     esi
0x40e2a5  pop     edi
0x40e2a6  retn
0x40e2a8  mov     al, [esi+3]; jumptable 0040E288 case 1
0x40e2ab  mov     [edi+3], al
0x40e2ae  mov     eax, [esp+8+arg_0]
0x40e2b2  pop     esi
0x40e2b3  pop     edi
0x40e2b4  retn
0x40e2b8  mov     al, [esi+3]; jumptable 0040E288 case 2
0x40e2bb  mov     [edi+3], al
0x40e2be  mov     al, [esi+2]
0x40e2c1  mov     [edi+2], al
0x40e2c4  mov     eax, [esp+8+arg_0]
0x40e2c8  pop     esi
0x40e2c9  pop     edi
0x40e2ca  retn
0x40e2cc  mov     al, [esi+3]; jumptable 0040E288 case 3
0x40e2cf  mov     [edi+3], al
0x40e2d2  mov     al, [esi+2]
0x40e2d5  mov     [edi+2], al
0x40e2d8  mov     al, [esi+1]
0x40e2db  mov     [edi+1], al
0x40e2de  mov     eax, [esp+8+arg_0]
0x40e2e2  pop     esi
0x40e2e3  pop     edi
0x40e2e4  retn
0x40e2e5  test    edi, 0Fh
0x40e2eb  jz      short XmmMovLargeLoop
0x40e2ed  dec     ecx
0x40e2ee  dec     esi
0x40e2ef  dec     edi
0x40e2f0  mov     al, [esi]
0x40e2f2  mov     [edi], al
0x40e2f4  test    edi, 0Fh
0x40e2fa  jnz     short XmmMovAlignLoop
0x40e2fc  cmp     ecx, 80h
0x40e302  jb      short XmmMovSmallTest
0x40e304  sub     esi, 80h
0x40e30a  sub     edi, 80h
0x40e310  movdqu  xmm0, xmmword ptr [esi]
0x40e314  movdqu  xmm1, xmmword ptr [esi+10h]
0x40e319  movdqu  xmm2, xmmword ptr [esi+20h]
0x40e31e  movdqu  xmm3, xmmword ptr [esi+30h]
0x40e323  movdqu  xmm4, xmmword ptr [esi+40h]
0x40e328  movdqu  xmm5, xmmword ptr [esi+50h]
0x40e32d  movdqu  xmm6, xmmword ptr [esi+60h]
0x40e332  movdqu  xmm7, xmmword ptr [esi+70h]
0x40e337  movdqu  xmmword ptr [edi], xmm0
0x40e33b  movdqu  xmmword ptr [edi+10h], xmm1
0x40e340  movdqu  xmmword ptr [edi+20h], xmm2
0x40e345  movdqu  xmmword ptr [edi+30h], xmm3
0x40e34a  movdqu  xmmword ptr [edi+40h], xmm4
0x40e34f  movdqu  xmmword ptr [edi+50h], xmm5
0x40e354  movdqu  xmmword ptr [edi+60h], xmm6
0x40e359  movdqu  xmmword ptr [edi+70h], xmm7
0x40e35e  sub     ecx, 80h
0x40e364  test    ecx, 0FFFFFF80h
0x40e36a  jnz     short XmmMovLargeLoop
0x40e36c  cmp     ecx, 20h ; ' '
0x40e36f  jb      short CopyDownSmall
0x40e371  sub     esi, 20h ; ' '
0x40e374  sub     edi, 20h ; ' '
0x40e377  movdqu  xmm0, xmmword ptr [esi]
0x40e37b  movdqu  xmm1, xmmword ptr [esi+10h]
0x40e380  movdqu  xmmword ptr [edi], xmm0
0x40e384  movdqu  xmmword ptr [edi+10h], xmm1
0x40e389  sub     ecx, 20h ; ' '
0x40e38c  test    ecx, 0FFFFFFE0h
0x40e392  jnz     short XmmMovSmallLoop
0x40e394  test    ecx, 0FFFFFFFCh
0x40e39a  jz      short CopyDownByteTest
0x40e39c  sub     edi, 4
0x40e39f  sub     esi, 4
0x40e3a2  mov     eax, [esi]
0x40e3a4  mov     [edi], eax
0x40e3a6  sub     ecx, 4
0x40e3a9  test    ecx, 0FFFFFFFCh
0x40e3af  jnz     short CopyDownDwordLoop
0x40e3b1  test    ecx, ecx
0x40e3b3  jz      short CopyDownReturn
  ... truncated ...
```
