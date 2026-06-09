# FilterEdgeHor_Short_8_Complex_SSE2

- ea: `0x180038f7c`
- end: `0x180039286`
- name: `FilterEdgeHor_Short_8_Complex_SSE2`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003928c`

## pseudocode

```c
__int8 *__fastcall FilterEdgeHor_Short_8_Complex_SSE2(__m128i *a1, int a2, const __m128i *a3)
{
  __int64 v3; // r10
  __m128i *v4; // r9
  __int64 v5; // rdx
  __m128 v6; // xmm14
  __m128i v7; // xmm2
  __m128 v8; // xmm15
  __m128i v9; // xmm1
  __int8 *result; // rax
  __m128i v11; // xmm5
  __m128i v12; // xmm6
  __m128i v13; // xmm0
  __m128i v14; // xmm3
  __m128i v15; // xmm7
  __m128i v16; // xmm1
  __m128i v17; // xmm2
  __m128i v18; // xmm5
  __m128i v19; // xmm0
  __m128i v20; // xmm4
  __m128i v21; // xmm8
  __m128i v22; // xmm3
  __m128i v23; // xmm1
  __m128i v24; // xmm6
  __m128i v25; // xmm0
  __m128i v26; // xmm2
  __m128i v27; // xmm7
  __m128i v28; // xmm5
  __m128i v29; // xmm10
  __m128i v30; // xmm4
  __m128i v31; // xmm0
  __m128i v32; // xmm6
  __m128 v33; // xmm11
  __m128i v34; // xmm8
  __m128i v35; // xmm1
  __m128i v36; // xmm4
  __m128i v37; // xmm9
  __m128i si128; // xmm0
  __m128i v39; // xmm12
  __m128i v40; // xmm10
  __m128i v41; // xmm9
  __m128i v42; // xmm6
  __m128i v43; // xmm2
  __m128i v44; // xmm7
  __m128i v45; // xmm6
  __m128i v46; // xmm5
  __m128 v47; // xmm1
  __m128i v48; // xmm5
  __m128i v49; // xmm3
  __m128i v50; // xmm12
  __m128i v51; // xmm2
  __m128 v52; // [rsp+0h] [rbp-C8h]
  __m128 v53; // [rsp+10h] [rbp-B8h]

  v3 = a2;
  v4 = (__m128i *)((char *)a1 - a2);
  v5 = 2 * a2;
  v6 = (__m128)_mm_loadl_epi64((__m128i *)((char *)a1 + v3));
  v7 = _mm_unpacklo_epi8(_mm_loadu_si128(a3), (__m128i)0LL);
  v8 = (__m128)_mm_loadl_epi64(a1);
  v9 = _mm_add_epi16(v7, v7);
  result = &a1->m128i_i8[-v5];
  v11 = _mm_unpacklo_epi8(_mm_loadl_epi64((__m128i *)((char *)v4 - v5)), (__m128i)0LL);
  v12 = _mm_add_epi16(v11, v9);
  v13 = _mm_add_epi16(_mm_add_epi16(v11, v11), _mm_add_epi16(v9, v7));
  v52 = (__m128)_mm_loadl_epi64((__m128i *)((char *)a1 - v5));
  v14 = _mm_unpacklo_epi8((__m128i)v52, (__m128i)0LL);
  v15 = _mm_add_epi16(v14, _mm_add_epi16(v11, v7));
  v16 = _mm_add_epi16(v14, v11);
  v17 = _mm_add_epi16(v14, v13);
  v53 = (__m128)_mm_loadl_epi64(v4);
  v18 = _mm_unpacklo_epi8((__m128i)v53, (__m128i)0LL);
  v19 = _mm_add_epi16(_mm_add_epi16(v14, v14), v12);
  v20 = _mm_add_epi16(v18, v14);
  v21 = _mm_add_epi16(v18, v16);
  v22 = _mm_add_epi16(v18, v17);
  v23 = _mm_add_epi16(v18, v19);
  v24 = _mm_unpacklo_epi8((__m128i)v8, (__m128i)0LL);
  v25 = _mm_add_epi16(_mm_add_epi16(v18, v18), v15);
  v26 = _mm_add_epi16(v24, v18);
  v27 = _mm_unpacklo_epi8((__m128i)v6, (__m128i)0LL);
  v28 = _mm_add_epi16(v24, v20);
  v29 = _mm_add_epi16(v24, v22);
  v30 = _mm_add_epi16(v24, v25);
  v31 = _mm_add_epi16(v24, v23);
  v32 = _mm_add_epi16(_mm_add_epi16(v24, v24), v21);
  v33 = (__m128)_mm_loadl_epi64((__m128i *)((char *)a1 + v5));
  v34 = _mm_add_epi16(v27, v26);
  v35 = _mm_add_epi16(v27, v30);
  v36 = _mm_unpacklo_epi8(_mm_loadu_si128(a3 + 1), (__m128i)0LL);
  v37 = _mm_add_epi16(v27, v31);
  si128 = _mm_load_si128((const __m128i *)&xmmword_180050430);
  v39 = _mm_unpacklo_epi8((__m128i)v33, (__m128i)0LL);
  v40 = _mm_srli_epi16(_mm_add_epi16(v29, si128), 3u);
  v41 = _mm_srli_epi16(_mm_add_epi16(v37, si128), 3u);
  v42 = _mm_add_epi16(v39, _mm_add_epi16(v27, v32));
  v43 = v39;
  v44 = _mm_add_epi16(_mm_add_epi16(v27, v27), v28);
  v45 = _mm_srli_epi16(_mm_add_epi16(_mm_add_epi16(v42, v36), si128), 3u);
  v46 = _mm_add_epi16(v39, v35);
  v47 = (__m128)_mm_loadu_si128(a3 + 2);
  v48 = _mm_srli_epi16(_mm_add_epi16(v46, si128), 3u);
  v49 = _mm_add_epi16(v36, v36);
  v50 = _mm_srli_epi16(
          _mm_add_epi16(_mm_add_epi16(_mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v39, v39), v34), v36), v49), si128),
          3u);
  v51 = _mm_srli_epi16(_mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v43, v44), v49), si128), 3u);
  *(__int64 *)((char *)v4->m128i_i64 - v5) = _mm_packus_epi16(v40, v40).m128i_u64[0] & v47.m128_u64[0]
                                           | _mm_andnot_ps(v47, (__m128)_mm_loadl_epi64((__m128i *)((char *)v4 - v5))).m128_u64[0];
  *(__int64 *)((char *)a1->m128i_i64 - v5) = _mm_packus_epi16(v41, v41).m128i_u64[0] & v47.m128_u64[0]
                                           | _mm_andnot_ps(v47, v52).m128_u64[0];
  v4->m128i_i64[0] = _mm_packus_epi16(v48, v48).m128i_u64[0] & v47.m128_u64[0] | _mm_andnot_ps(v47, v53).m128_u64[0];
  a1->m128i_i64[0] = _mm_packus_epi16(v45, v45).m128i_u64[0] & v47.m128_u64[0] | _mm_andnot_ps(v47, v8).m128_u64[0];
  *(__int64 *)((char *)a1->m128i_i64 + v3) = _mm_packus_epi16(v51, v51).m128i_u64[0] & v47.m128_u64[0]
                                           | _mm_andnot_ps(v47, v6).m128_u64[0];
  *(__int64 *)((char *)a1->m128i_i64 + v5) = _mm_packus_epi16(v50, v50).m128i_u64[0] & v47.m128_u64[0]
                                           | _mm_andnot_ps(v47, v33).m128_u64[0];
  return result;
}

```

## disassembly

```asm
0x180038f7c  mov     rax, rsp
0x180038f7f  sub     rsp, 0C8h
0x180038f86  movdqu  xmm2, xmmword ptr [r8]
0x180038f8b  mov     r11, rcx
0x180038f8e  movaps  xmmword ptr [rax-18h], xmm6
0x180038f92  mov     r9, rcx
0x180038f95  movaps  xmmword ptr [rax-28h], xmm7
0x180038f99  movaps  xmmword ptr [rax-38h], xmm8
0x180038f9e  movaps  xmmword ptr [rax-48h], xmm9
0x180038fa3  movaps  xmmword ptr [rax-58h], xmm10
0x180038fa8  movaps  xmmword ptr [rax-68h], xmm11
0x180038fad  movaps  xmmword ptr [rax-78h], xmm12
0x180038fb2  lea     eax, [rdx+rdx]
0x180038fb5  movsxd  r10, edx
0x180038fb8  sub     r9, r10
0x180038fbb  movsxd  rdx, eax
0x180038fbe  movaps  [rsp+0C8h+var_88], xmm13
0x180038fc4  mov     rcx, r9
0x180038fc7  xorps   xmm13, xmm13
0x180038fcb  movaps  [rsp+0C8h+var_98], xmm14
0x180038fd1  movq    xmm14, qword ptr [r10+r11]
0x180038fd7  sub     rcx, rdx
0x180038fda  punpcklbw xmm2, xmm13
0x180038fdf  mov     rax, r11
0x180038fe2  movaps  [rsp+0C8h+var_A8], xmm15
0x180038fe8  movdqa  xmm1, xmm2
0x180038fec  movq    xmm15, qword ptr [r11]
0x180038ff1  paddw   xmm1, xmm2
0x180038ff5  movq    xmm5, qword ptr [rcx]
0x180038ff9  sub     rax, rdx
0x180038ffc  punpcklbw xmm5, xmm13
0x180039001  movdqa  xmm6, xmm5
0x180039005  movdqa  xmm0, xmm5
0x180039009  paddw   xmm0, xmm5
0x18003900d  paddw   xmm6, xmm1
0x180039011  paddw   xmm1, xmm2
0x180039015  movdqa  xmm4, xmm5
0x180039019  paddw   xmm0, xmm1
0x18003901d  paddw   xmm4, xmm2
0x180039021  movq    xmm1, qword ptr [rax]
0x180039025  movdqa  xmm3, xmm1
0x180039029  movdqa  [rsp+0C8h+var_C8], xmm1
0x18003902e  punpcklbw xmm3, xmm13
0x180039033  movdqa  xmm7, xmm3
0x180039037  movdqa  xmm1, xmm3
0x18003903b  paddw   xmm7, xmm4
0x18003903f  paddw   xmm1, xmm5
0x180039043  movq    xmm4, qword ptr [r9]
0x180039048  movdqa  xmm2, xmm3
0x18003904c  paddw   xmm2, xmm0
0x180039050  movdqa  [rsp+0C8h+var_B8], xmm4
0x180039056  movdqa  xmm5, xmm4
0x18003905a  movdqa  xmm0, xmm3
0x18003905e  punpcklbw xmm5, xmm13
0x180039063  paddw   xmm0, xmm3
0x180039067  paddw   xmm0, xmm6
0x18003906b  movdqa  xmm4, xmm5
0x18003906f  paddw   xmm4, xmm3
0x180039073  movdqa  xmm8, xmm5
0x180039078  paddw   xmm8, xmm1
0x18003907d  movdqa  xmm3, xmm5
0x180039081  movdqa  xmm1, xmm5
0x180039085  paddw   xmm3, xmm2
0x180039089  paddw   xmm1, xmm0
0x18003908d  movdqa  xmm6, xmm15
0x180039092  punpcklbw xmm6, xmm13
0x180039097  movdqa  xmm0, xmm5
0x18003909b  paddw   xmm0, xmm5
0x18003909f  movdqa  xmm2, xmm6
0x1800390a3  paddw   xmm0, xmm7
0x1800390a7  movdqa  xmm10, xmm6
0x1800390ac  paddw   xmm2, xmm5
0x1800390b0  movdqa  xmm7, xmm14
0x1800390b5  movdqa  xmm5, xmm6
0x1800390b9  punpcklbw xmm7, xmm13
0x1800390be  paddw   xmm5, xmm4
0x1800390c2  paddw   xmm10, xmm3
0x1800390c7  movdqa  xmm4, xmm6
0x1800390cb  paddw   xmm4, xmm0
0x1800390cf  movdqa  xmm0, xmm6
0x1800390d3  paddw   xmm6, xmm6
0x1800390d7  paddw   xmm0, xmm1
0x1800390db  paddw   xmm6, xmm8
0x1800390e0  movq    xmm11, qword ptr [rdx+r11]
0x1800390e6  movdqa  xmm8, xmm7
0x1800390eb  paddw   xmm8, xmm2
0x1800390f0  movdqa  xmm1, xmm7
0x1800390f4  paddw   xmm1, xmm4
0x1800390f8  movdqa  xmm2, xmm7
0x1800390fc  movdqu  xmm4, xmmword ptr [r8+10h]
0x180039102  paddw   xmm2, xmm6
0x180039106  punpcklbw xmm4, xmm13
0x18003910b  movdqa  xmm9, xmm7
0x180039110  paddw   xmm9, xmm0
0x180039115  movdqa  xmm12, xmm11
0x18003911a  movdqa  xmm0, cs:xmmword_180050430
0x180039122  paddw   xmm7, xmm7
0x180039126  paddw   xmm10, xmm0
0x18003912b  punpcklbw xmm12, xmm13
0x180039130  paddw   xmm9, xmm0
0x180039135  psrlw   xmm10, 3
0x18003913b  movdqa  xmm6, xmm12
0x180039140  psrlw   xmm9, 3
0x180039146  paddw   xmm6, xmm2
0x18003914a  packuswb xmm10, xmm10
0x18003914f  movdqa  xmm2, xmm12
0x180039154  packuswb xmm9, xmm9
0x180039159  paddw   xmm7, xmm5
0x18003915d  paddw   xmm6, xmm4
0x180039161  paddw   xmm6, xmm0
0x180039165  movdqa  xmm5, xmm12
0x18003916a  paddw   xmm12, xmm12
0x18003916f  psrlw   xmm6, 3
0x180039174  paddw   xmm12, xmm8
0x180039179  packuswb xmm6, xmm6
0x18003917d  paddw   xmm5, xmm1
0x180039181  paddw   xmm12, xmm4
0x180039186  movdqu  xmm1, xmmword ptr [r8+20h]
0x18003918c  paddw   xmm5, xmm0
0x180039190  paddw   xmm2, xmm7
0x180039194  psrlw   xmm5, 3
0x180039199  andps   xmm6, xmm1
0x18003919c  packuswb xmm5, xmm5
0x1800391a0  andps   xmm10, xmm1
0x1800391a4  andps   xmm9, xmm1
0x1800391a8  andps   xmm5, xmm1
0x1800391ab  movdqa  xmm3, xmm4
0x1800391af  paddw   xmm3, xmm4
0x1800391b3  paddw   xmm12, xmm3
0x1800391b8  paddw   xmm2, xmm3
0x1800391bc  movq    xmm3, qword ptr [rcx]
0x1800391c0  paddw   xmm12, xmm0
0x1800391c5  paddw   xmm2, xmm0
0x1800391c9  psrlw   xmm12, 3
0x1800391cf  psrlw   xmm2, 3
0x1800391d4  movdqa  xmm0, xmm1
0x1800391d8  andnps  xmm0, xmm3
0x1800391db  packuswb xmm2, xmm2
0x1800391df  orps    xmm10, xmm0
0x1800391e3  packuswb xmm12, xmm12
0x1800391e8  movq    qword ptr [rcx], xmm10
0x1800391ed  movdqa  xmm0, xmm1
0x1800391f1  andnps  xmm0, [rsp+0C8h+var_C8]
0x1800391f5  andps   xmm2, xmm1
0x1800391f8  orps    xmm9, xmm0
0x1800391fc  andps   xmm12, xmm1
0x180039200  movq    qword ptr [rax], xmm9
0x180039205  movdqa  xmm0, xmm1
0x180039209  andnps  xmm0, [rsp+0C8h+var_B8]
0x18003920e  orps    xmm5, xmm0
0x180039211  movdqa  xmm0, xmm1
0x180039215  andnps  xmm0, xmm15
0x180039219  movq    qword ptr [r9], xmm5
0x18003921e  orps    xmm6, xmm0
0x180039221  movdqa  xmm0, xmm1
0x180039225  movq    qword ptr [r11], xmm6
0x18003922a  andnps  xmm0, xmm14
0x18003922e  andnps  xmm1, xmm11
0x180039232  orps    xmm2, xmm0
0x180039235  movq    qword ptr [r10+r11], xmm2
0x18003923b  orps    xmm12, xmm1
0x18003923f  movq    qword ptr [rdx+r11], xmm12
0x180039245  lea     r11, [rsp+0C8h]
0x18003924d  movaps  xmm6, xmmword ptr [r11-18h]
0x180039252  movaps  xmm7, xmmword ptr [r11-28h]
0x180039257  movaps  xmm8, xmmword ptr [r11-38h]
0x18003925c  movaps  xmm9, xmmword ptr [r11-48h]
0x180039261  movaps  xmm10, xmmword ptr [r11-58h]
0x180039266  movaps  xmm11, xmmword ptr [r11-68h]
0x18003926b  movaps  xmm12, xmmword ptr [r11-78h]
0x180039270  movaps  xmm13, [rsp+0C8h+var_88]
0x180039276  movaps  xmm14, [rsp+0C8h+var_98]
0x18003927c  movaps  xmm15, [rsp+0C8h+var_A8]
0x180039282  mov     rsp, r11
0x180039285  retn
```
