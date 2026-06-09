# _memmove

- ea: `0x40cb40`
- end: `0x40d0b4`
- name: `_memmove`
- size: `1396`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x407fd4`
- `0x408220`
- `0x408306`
- `0x4087ac`
- `0x408c21`
- `0x408cbc`
- `0x409e18`
- `0x409e7a`
- `0x409eba`
- `0x409f30`
- `0x409fc9`
- `0x40a05f`
- `0x40a0b1`
- `0x40a0fe`
- `0x40a410`
- `0x40a581`
- `0x40a616`
- `0x40a6a7`
- `0x40a75a`
- `0x40a7db`
- `0x40aab8`
- `0x40ade6`
- `0x410cee`
- `0x410ef3`
- `0x4137a5`

## callees

- `0x40cb40`

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
      if ( _bittest(&dword_417010, 1u) )
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
      if ( !_bittest(&dword_417010, 1u) )
        goto Dword_align;
      goto XmmCopySmallTest;
    }
    if ( _bittest(&dword_417D10, 1u) )
    {
      qmemcpy(a1, Src, Size);
      return a1;
    }
    if ( (((unsigned int)Src ^ (unsigned int)a1) & 0xF) == 0 && _bittest(&dword_417010, 1u) )
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
    if ( !_bittest(&dword_417D10, 0) || ((unsigned __int8)a1 & 3) != 0 )
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
0x40cb40  push    edi
0x40cb41  push    esi
0x40cb42  mov     esi, [esp+8+Src]
0x40cb46  mov     ecx, [esp+8+Size]
0x40cb4a  mov     edi, [esp+8+arg_0]
0x40cb4e  mov     eax, ecx
0x40cb50  mov     edx, ecx
0x40cb52  add     eax, esi
0x40cb54  cmp     edi, esi
0x40cb56  jbe     short CopyUp
0x40cb58  cmp     edi, eax
0x40cb5a  jb      CopyDown
0x40cb60  cmp     ecx, 20h ; ' '
0x40cb63  jb      CopyUpDwordMov
0x40cb69  cmp     ecx, 80h
0x40cb6f  jnb     short CopyUpLargeMov
0x40cb71  bt      dword_417010, 1
0x40cb79  jb      XmmCopySmallTest
0x40cb7f  jmp     Dword_align
0x40cb84  bt      dword_417D10, 1
0x40cb8c  jnb     short CopyUpSSE2Check
0x40cb8e  rep movsb
0x40cb90  mov     eax, [esp+8+arg_0]
0x40cb94  pop     esi
0x40cb95  pop     edi
0x40cb96  retn
0x40cb97  mov     eax, edi
0x40cb99  xor     eax, esi
0x40cb9b  test    eax, 0Fh
0x40cba0  jnz     short AtomChk
0x40cba2  bt      dword_417010, 1
0x40cbaa  jb      XmmCopy
0x40cbb0  bt      dword_417D10, 0
0x40cbb8  jnb     Dword_align
0x40cbbe  test    edi, 3
0x40cbc4  jnz     Dword_align
0x40cbca  test    esi, 3
0x40cbd0  jnz     Dword_align_Ok
0x40cbd6  bt      edi, 2
0x40cbda  jnb     short PalignHead8
0x40cbdc  mov     eax, [esi]
0x40cbde  sub     ecx, 4
0x40cbe1  lea     esi, [esi+4]
0x40cbe4  mov     [edi], eax
0x40cbe6  lea     edi, [edi+4]
0x40cbe9  bt      edi, 3
0x40cbed  jnb     short PalignLoop
0x40cbef  movq    xmm1, qword ptr [esi]
0x40cbf3  sub     ecx, 8
0x40cbf6  lea     esi, [esi+8]
0x40cbf9  movq    qword ptr [edi], xmm1
0x40cbfd  lea     edi, [edi+8]
0x40cc00  test    esi, 7
0x40cc06  jz      short MovPalign8
0x40cc08  bt      esi, 3
0x40cc0c  jnb     MovPalign4
0x40cc12  movdqa  xmm1, xmmword ptr [esi-0Ch]
0x40cc17  lea     esi, [esi-0Ch]
0x40cc1a  mov     edi, edi
0x40cc1c  movdqa  xmm3, xmmword ptr [esi+10h]
0x40cc21  sub     ecx, 30h ; '0'
0x40cc24  movdqa  xmm0, xmmword ptr [esi+20h]
0x40cc29  movdqa  xmm5, xmmword ptr [esi+30h]
0x40cc2e  lea     esi, [esi+30h]
0x40cc31  cmp     ecx, 30h ; '0'
0x40cc34  movdqa  xmm2, xmm3
0x40cc38  palignr xmm3, xmm1, 0Ch
0x40cc3e  movdqa  xmmword ptr [edi], xmm3
0x40cc42  movdqa  xmm4, xmm0
0x40cc46  palignr xmm0, xmm2, 0Ch
0x40cc4c  movdqa  xmmword ptr [edi+10h], xmm0
0x40cc51  movdqa  xmm1, xmm5
0x40cc55  palignr xmm5, xmm4, 0Ch
0x40cc5b  movdqa  xmmword ptr [edi+20h], xmm5
0x40cc60  lea     edi, [edi+30h]
0x40cc63  jnb     short PalignLoop12
0x40cc65  lea     esi, [esi+0Ch]
0x40cc68  jmp     PalignTail
0x40cc6d  movdqa  xmm1, xmmword ptr [esi-8]
0x40cc72  lea     esi, [esi-8]
0x40cc75  lea     ecx, [ecx+0]
0x40cc78  movdqa  xmm3, xmmword ptr [esi+10h]
0x40cc7d  sub     ecx, 30h ; '0'
0x40cc80  movdqa  xmm0, xmmword ptr [esi+20h]
0x40cc85  movdqa  xmm5, xmmword ptr [esi+30h]
0x40cc8a  lea     esi, [esi+30h]
0x40cc8d  cmp     ecx, 30h ; '0'
0x40cc90  movdqa  xmm2, xmm3
0x40cc94  palignr xmm3, xmm1, 8
0x40cc9a  movdqa  xmmword ptr [edi], xmm3
0x40cc9e  movdqa  xmm4, xmm0
0x40cca2  palignr xmm0, xmm2, 8
0x40cca8  movdqa  xmmword ptr [edi+10h], xmm0
0x40ccad  movdqa  xmm1, xmm5
0x40ccb1  palignr xmm5, xmm4, 8
0x40ccb7  movdqa  xmmword ptr [edi+20h], xmm5
0x40ccbc  lea     edi, [edi+30h]
0x40ccbf  jnb     short PalignLoop8
0x40ccc1  lea     esi, [esi+8]
0x40ccc4  jmp     short PalignTail
0x40ccc6  movdqa  xmm1, xmmword ptr [esi-4]
0x40cccb  lea     esi, [esi-4]
0x40ccce  mov     edi, edi
0x40ccd0  movdqa  xmm3, xmmword ptr [esi+10h]
0x40ccd5  sub     ecx, 30h ; '0'
0x40ccd8  movdqa  xmm0, xmmword ptr [esi+20h]
0x40ccdd  movdqa  xmm5, xmmword ptr [esi+30h]
0x40cce2  lea     esi, [esi+30h]
0x40cce5  cmp     ecx, 30h ; '0'
0x40cce8  movdqa  xmm2, xmm3
0x40ccec  palignr xmm3, xmm1, 4
0x40ccf2  movdqa  xmmword ptr [edi], xmm3
0x40ccf6  movdqa  xmm4, xmm0
0x40ccfa  palignr xmm0, xmm2, 4
0x40cd00  movdqa  xmmword ptr [edi+10h], xmm0
0x40cd05  movdqa  xmm1, xmm5
0x40cd09  palignr xmm5, xmm4, 4
0x40cd0f  movdqa  xmmword ptr [edi+20h], xmm5
0x40cd14  lea     edi, [edi+30h]
0x40cd17  jnb     short PalignLoop4
0x40cd19  lea     esi, [esi+4]
0x40cd1c  cmp     ecx, 10h
0x40cd1f  jb      short PalignTail4
0x40cd21  movdqu  xmm1, xmmword ptr [esi]; jumptable 0040CD65 default case
0x40cd25  sub     ecx, 10h
0x40cd28  lea     esi, [esi+10h]
0x40cd2b  movdqa  xmmword ptr [edi], xmm1
0x40cd2f  lea     edi, [edi+10h]
0x40cd32  jmp     short PalignTail
0x40cd34  bt      ecx, 2
0x40cd38  jnb     short PalignTail8
0x40cd3a  mov     eax, [esi]
0x40cd3c  sub     ecx, 4
0x40cd3f  lea     esi, [esi+4]
0x40cd42  mov     [edi], eax
0x40cd44  lea     edi, [edi+4]
0x40cd47  bt      ecx, 3
0x40cd4b  jnb     short PalignTailLE3
0x40cd4d  movq    xmm1, qword ptr [esi]
0x40cd51  sub     ecx, 8
0x40cd54  lea     esi, [esi+8]
0x40cd57  movq    qword ptr [edi], xmm1
0x40cd5b  lea     edi, [edi+8]
0x40cd5e  mov     eax, ds:jpt_40CD65[ecx*4]; switch 4 cases
0x40cd65  jmp     eax; switch jump
0x40cd67  test    edi, 3
0x40cd6d  jz      short Dword_align_Ok
0x40cd6f  mov     al, [esi]
0x40cd71  mov     [edi], al
0x40cd73  dec     ecx
0x40cd74  add     esi, 1
0x40cd77  add     edi, 1
0x40cd7a  test    edi, 3
0x40cd80  jnz     short Dword_up_align_loop
0x40cd82  mov     edx, ecx
0x40cd84  cmp     ecx, 20h ; ' '
0x40cd87  jb      CopyUpDwordMov
0x40cd8d  shr     ecx, 2
0x40cd90  rep movsd
0x40cd92  and     edx, 3
0x40cd95  jmp     ds:jpt_40CD65[edx*4]; switch 4 cases
0x40cd9c  jmp     dword ptr ds:TrailingUp0[ecx*4]; jumptable 0040CD65 case 0
0x40cdb4  mov     eax, [esp+8+arg_0]; jumptable 0040CD65 case 0
0x40cdb8  pop     esi
0x40cdb9  pop     edi
0x40cdba  retn
0x40cdbc  mov     al, [esi]; jumptable 0040CD65 case 1
0x40cdbe  mov     [edi], al
0x40cdc0  mov     eax, [esp+8+arg_0]
0x40cdc4  pop     esi
0x40cdc5  pop     edi
0x40cdc6  retn
0x40cdc8  mov     al, [esi]; jumptable 0040CD65 case 2
0x40cdca  mov     [edi], al
0x40cdcc  mov     al, [esi+1]
0x40cdcf  mov     [edi+1], al
0x40cdd2  mov     eax, [esp+8+arg_0]
0x40cdd6  pop     esi
0x40cdd7  pop     edi
0x40cdd8  retn
0x40cddc  mov     al, [esi]; jumptable 0040CD65 case 3
0x40cdde  mov     [edi], al
0x40cde0  mov     al, [esi+1]
0x40cde3  mov     [edi+1], al
0x40cde6  mov     al, [esi+2]
0x40cde9  mov     [edi+2], al
0x40cdec  mov     eax, [esp+8+arg_0]
0x40cdf0  pop     esi
0x40cdf1  pop     edi
0x40cdf2  retn
0x40cdf4  lea     esi, [esi+ecx]
0x40cdf7  lea     edi, [edi+ecx]
0x40cdfa  cmp     ecx, 20h ; ' '
0x40cdfd  jb      CopyDownSmall
0x40ce03  bt      dword_417010, 1
0x40ce0b  jb      XmmMovLargeAlignTest
0x40ce11  test    edi, 3
0x40ce17  jz      short CopyDownAligned
0x40ce19  mov     edx, edi
0x40ce1b  and     edx, 3
0x40ce1e  sub     ecx, edx
0x40ce20  mov     al, [esi-1]
0x40ce23  mov     [edi-1], al
0x40ce26  dec     esi
0x40ce27  dec     edi
0x40ce28  sub     edx, 1
0x40ce2b  jnz     short CopyDownAlignLoop
0x40ce2d  cmp     ecx, 20h ; ' '
0x40ce30  jb      CopyDownSmall
0x40ce36  mov     edx, ecx
0x40ce38  shr     ecx, 2
0x40ce3b  and     edx, 3
0x40ce3e  sub     esi, 4
0x40ce41  sub     edi, 4
0x40ce44  std
0x40ce45  rep movsd
0x40ce47  cld
0x40ce48  jmp     ds:jpt_40CE48[edx*4]; switch 4 cases
0x40ce60  mov     eax, [esp+8+arg_0]; jumptable 0040CE48 case 0
0x40ce64  pop     esi
0x40ce65  pop     edi
0x40ce66  retn
0x40ce68  mov     al, [esi+3]; jumptable 0040CE48 case 1
0x40ce6b  mov     [edi+3], al
0x40ce6e  mov     eax, [esp+8+arg_0]
0x40ce72  pop     esi
0x40ce73  pop     edi
0x40ce74  retn
0x40ce78  mov     al, [esi+3]; jumptable 0040CE48 case 2
0x40ce7b  mov     [edi+3], al
0x40ce7e  mov     al, [esi+2]
0x40ce81  mov     [edi+2], al
0x40ce84  mov     eax, [esp+8+arg_0]
0x40ce88  pop     esi
0x40ce89  pop     edi
0x40ce8a  retn
0x40ce8c  mov     al, [esi+3]; jumptable 0040CE48 case 3
0x40ce8f  mov     [edi+3], al
0x40ce92  mov     al, [esi+2]
0x40ce95  mov     [edi+2], al
0x40ce98  mov     al, [esi+1]
0x40ce9b  mov     [edi+1], al
0x40ce9e  mov     eax, [esp+8+arg_0]
0x40cea2  pop     esi
0x40cea3  pop     edi
0x40cea4  retn
0x40cea5  test    edi, 0Fh
0x40ceab  jz      short XmmMovLargeLoop
0x40cead  dec     ecx
0x40ceae  dec     esi
0x40ceaf  dec     edi
0x40ceb0  mov     al, [esi]
0x40ceb2  mov     [edi], al
0x40ceb4  test    edi, 0Fh
0x40ceba  jnz     short XmmMovAlignLoop
0x40cebc  cmp     ecx, 80h
0x40cec2  jb      short XmmMovSmallTest
0x40cec4  sub     esi, 80h
0x40ceca  sub     edi, 80h
0x40ced0  movdqu  xmm0, xmmword ptr [esi]
0x40ced4  movdqu  xmm1, xmmword ptr [esi+10h]
0x40ced9  movdqu  xmm2, xmmword ptr [esi+20h]
0x40cede  movdqu  xmm3, xmmword ptr [esi+30h]
0x40cee3  movdqu  xmm4, xmmword ptr [esi+40h]
0x40cee8  movdqu  xmm5, xmmword ptr [esi+50h]
0x40ceed  movdqu  xmm6, xmmword ptr [esi+60h]
0x40cef2  movdqu  xmm7, xmmword ptr [esi+70h]
0x40cef7  movdqu  xmmword ptr [edi], xmm0
0x40cefb  movdqu  xmmword ptr [edi+10h], xmm1
0x40cf00  movdqu  xmmword ptr [edi+20h], xmm2
0x40cf05  movdqu  xmmword ptr [edi+30h], xmm3
0x40cf0a  movdqu  xmmword ptr [edi+40h], xmm4
0x40cf0f  movdqu  xmmword ptr [edi+50h], xmm5
0x40cf14  movdqu  xmmword ptr [edi+60h], xmm6
0x40cf19  movdqu  xmmword ptr [edi+70h], xmm7
0x40cf1e  sub     ecx, 80h
0x40cf24  test    ecx, 0FFFFFF80h
0x40cf2a  jnz     short XmmMovLargeLoop
0x40cf2c  cmp     ecx, 20h ; ' '
0x40cf2f  jb      short CopyDownSmall
0x40cf31  sub     esi, 20h ; ' '
0x40cf34  sub     edi, 20h ; ' '
0x40cf37  movdqu  xmm0, xmmword ptr [esi]
0x40cf3b  movdqu  xmm1, xmmword ptr [esi+10h]
0x40cf40  movdqu  xmmword ptr [edi], xmm0
0x40cf44  movdqu  xmmword ptr [edi+10h], xmm1
0x40cf49  sub     ecx, 20h ; ' '
0x40cf4c  test    ecx, 0FFFFFFE0h
0x40cf52  jnz     short XmmMovSmallLoop
0x40cf54  test    ecx, 0FFFFFFFCh
0x40cf5a  jz      short CopyDownByteTest
0x40cf5c  sub     edi, 4
0x40cf5f  sub     esi, 4
0x40cf62  mov     eax, [esi]
0x40cf64  mov     [edi], eax
0x40cf66  sub     ecx, 4
0x40cf69  test    ecx, 0FFFFFFFCh
0x40cf6f  jnz     short CopyDownDwordLoop
0x40cf71  test    ecx, ecx
0x40cf73  jz      short CopyDownReturn
  ... truncated ...
```
