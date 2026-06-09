# FilterEdgeHor_8_Complex_SSE4

- ea: `0x180016e10`
- end: `0x1800171f3`
- name: `FilterEdgeHor_8_Complex_SSE4`
- size: `995`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800168c0`

## pseudocode

```c
__int8 *__fastcall FilterEdgeHor_8_Complex_SSE4(__m128i *a1, int a2, __int64 a3)
{
  __m128i v3; // xmm0
  __m128i v4; // xmm1
  __m128i v5; // xmm4
  __m128i *v8; // rbx
  __m128i v9; // xmm2
  __int64 v11; // r8
  __m128i v12; // xmm15
  __int64 v13; // rcx
  __m128i *v14; // r10
  __int8 *result; // rax
  __m128i v16; // xmm3
  __m128i v17; // xmm6
  __m128i v18; // xmm10
  __m128i v19; // xmm4
  __m128i v20; // xmm0
  __m128i v21; // xmm9
  __m128i v22; // xmm5
  __m128i v23; // xmm1
  __m128i v24; // xmm10
  __m128i v25; // xmm7
  __m128i v26; // xmm2
  __m128i v27; // xmm8
  __m128i v28; // xmm0
  __m128i v29; // xmm7
  __m128i v30; // xmm10
  __m128i v31; // xmm14
  __m128i v32; // xmm6
  __m128i v33; // xmm9
  __m128i v34; // xmm0
  __m128i v35; // xmm13
  __m128i v36; // xmm11
  __m128i v37; // xmm3
  __m128i v38; // xmm9
  __m128i v39; // xmm4
  __m128i v40; // xmm3
  __m128i v41; // xmm4
  __m128i v42; // xmm5
  __m128i v43; // xmm10
  __m128i v44; // xmm7
  __m128i v45; // xmm2
  __m128i v46; // xmm1
  __m128i v47; // xmm14
  __m128i v48; // xmm1
  __m128i v49; // xmm5
  __m128i v50; // xmm4
  __m128i v51; // xmm10
  __m128i v52; // xmm12
  __m128i v53; // xmm9
  __m128i si128; // xmm1
  __m128i v55; // xmm9
  __m128i v56; // xmm8
  __m128i v57; // xmm0
  __m128i v58; // xmm12
  __m128i v59; // xmm14
  __m128i v60; // xmm0
  __m128i v61; // xmm4
  __m128i v62; // xmm9
  __m128i v63; // xmm6
  __m128i v64; // xmm10
  __m128i v65; // xmm0
  __m128i v66; // xmm6
  __m128i v67; // xmm5
  __m128i v68; // xmm3
  __m128i v69; // xmm6
  __m128i v70; // xmm9
  __m128i v71; // xmm5
  __m128i v72; // xmm14
  __m128i v73; // xmm3
  __m128i v74; // xmm4
  __m128i v75; // xmm12
  __m128i v76; // xmm10
  __m128i v77; // xmm9
  __m128i v78; // xmm6
  __m128i v79; // xmm5
  __m128i v80; // xmm0
  __m128i v81; // xmm1
  __m128i v82; // xmm1
  __m128i v83; // [rsp+0h] [rbp-F8h] BYREF
  __m128i v84; // [rsp+10h] [rbp-E8h] BYREF
  __m128i v85; // [rsp+20h] [rbp-D8h] BYREF
  __m128i v86; // [rsp+30h] [rbp-C8h] BYREF
  __m128i v87; // [rsp+40h] [rbp-B8h] BYREF

  v3 = _mm_cvtepu8_epi16(*(__m64 *)a3);
  v4 = _mm_add_epi16(v3, v3);
  v5 = _mm_add_epi16(v4, v4);
  v8 = (__m128i *)((char *)a1 - a2);
  v9 = _mm_add_epi16(v5, v4);
  v11 = 4 * a2;
  v12 = _mm_loadl_epi64(v8);
  v13 = 2 * a2;
  v14 = (__m128i *)((char *)a1 - v11);
  result = &a1->m128i_i8[-v13];
  v85 = _mm_loadl_epi64(v14);
  v16 = _mm_cvtepu8_epi16(v85);
  v17 = _mm_add_epi16(v16, v3);
  v18 = _mm_add_epi16(v16, v16);
  v19 = _mm_add_epi16(v5, v18);
  v86 = _mm_loadl_epi64((__m128i *)((char *)v8 - v13));
  v20 = _mm_cvtepu8_epi16(v86);
  v21 = _mm_add_epi16(v20, v20);
  v22 = _mm_add_epi16(_mm_add_epi16(v18, v4), v21);
  v87 = _mm_loadl_epi64((__m128i *)((char *)a1 - v13));
  v23 = _mm_cvtepu8_epi16(v87);
  v24 = _mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v18, v18), v9), v21);
  v25 = _mm_add_epi16(v20, v16);
  v26 = _mm_cvtepu8_epi16(v12);
  v27 = _mm_add_epi16(v23, v20);
  v28 = _mm_add_epi16(v23, v23);
  v29 = _mm_add_epi16(v25, v28);
  v30 = _mm_add_epi16(v24, v28);
  v31 = _mm_add_epi16(_mm_add_epi16(v28, v28), v22);
  v32 = _mm_add_epi16(_mm_add_epi16(v17, v21), v28);
  v33 = _mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v21, v21), v19), v28);
  v34 = _mm_add_epi16(v26, v26);
  v35 = _mm_loadl_epi64(a1);
  v36 = _mm_loadl_epi64((__m128i *)((char *)a1 + a2));
  v37 = _mm_cvtepu8_epi16(v35);
  v38 = _mm_add_epi16(_mm_add_epi16(v33, v34), v37);
  v83 = _mm_add_epi16(_mm_add_epi16(v30, v26), v37);
  v39 = v37;
  v40 = _mm_add_epi16(v37, v37);
  v41 = _mm_add_epi16(v39, v26);
  v42 = _mm_add_epi16(_mm_add_epi16(v26, v23), v40);
  v43 = _mm_add_epi16(_mm_add_epi16(v40, v40), _mm_add_epi16(v29, v34));
  v44 = _mm_loadl_epi64((__m128i *)((char *)v8 + v11));
  v45 = _mm_cvtepu8_epi16(v44);
  v46 = _mm_cvtepu8_epi16(v36);
  v47 = _mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v31, v34), v40), v46);
  v84 = _mm_add_epi16(v38, v46);
  v48 = _mm_add_epi16(v46, v46);
  v49 = _mm_add_epi16(v42, v48);
  v50 = _mm_add_epi16(v41, v48);
  v51 = _mm_add_epi16(v43, v48);
  v52 = _mm_add_epi16(_mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v34, v34), v32), v40), v48);
  v53 = _mm_add_epi16(v48, v48);
  si128 = _mm_load_si128((const __m128i *)&xmmword_1800503F0);
  v55 = _mm_add_epi16(v53, _mm_add_epi16(_mm_add_epi16(v27, v34), v40));
  v56 = _mm_loadl_epi64((__m128i *)((char *)a1 + v13));
  v57 = _mm_cvtepu8_epi16(v56);
  v58 = _mm_add_epi16(v52, v57);
  v59 = _mm_add_epi16(v47, v57);
  v60 = _mm_add_epi16(v57, v57);
  v61 = _mm_add_epi16(v50, v60);
  v62 = _mm_add_epi16(v55, v60);
  v63 = _mm_add_epi16(v60, v60);
  v64 = _mm_add_epi16(_mm_add_epi16(v51, v60), v45);
  v65 = _mm_cvtepu8_epi16(*(__m64 *)(a3 + 16));
  v66 = _mm_add_epi16(v63, v49);
  v67 = _mm_add_epi16(v45, v45);
  v68 = _mm_add_epi16(v65, v65);
  v69 = _mm_add_epi16(v66, v67);
  v70 = _mm_add_epi16(_mm_add_epi16(v62, v67), v68);
  v71 = _mm_add_epi16(_mm_add_epi16(_mm_add_epi16(v67, v67), v61), v68);
  v72 = _mm_srli_epi16(_mm_add_epi16(v59, si128), 4u);
  v73 = _mm_add_epi16(v68, v68);
  v83 = _mm_srli_epi16(_mm_add_epi16(_mm_load_si128(&v83), si128), 4u);
  v74 = _mm_srli_epi16(_mm_add_epi16(_mm_load_si128(&v84), si128), 4u);
  v75 = _mm_srli_epi16(_mm_add_epi16(_mm_add_epi16(v58, v45), si128), 4u);
  v76 = _mm_srli_epi16(_mm_add_epi16(_mm_add_epi16(v64, v65), si128), 4u);
  v77 = _mm_srli_epi16(_mm_add_epi16(v70, si128), 4u);
  v78 = _mm_srli_epi16(_mm_add_epi16(_mm_add_epi16(v69, v73), si128), 4u);
  v79 = _mm_srli_epi16(_mm_add_epi16(_mm_add_epi16(v71, v73), si128), 4u);
  v80 = _mm_loadu_si128((const __m128i *)(a3 + 32));
  v81 = _mm_load_si128(&v83);
  v45.m128i_i64[0] = _mm_blendv_epi8(_mm_load_si128(&v85), _mm_packus_epi16(v81, v81), v80).m128i_u64[0];
  v82 = _mm_load_si128(&v86);
  v14->m128i_i64[0] = v45.m128i_i64[0];
  *(__int64 *)((char *)v8->m128i_i64 - v13) = _mm_blendv_epi8(v82, _mm_packus_epi16(v74, v74), v80).m128i_u64[0];
  *(__int64 *)((char *)a1->m128i_i64 - v13) = _mm_blendv_epi8(_mm_load_si128(&v87), _mm_packus_epi16(v72, v72), v80).m128i_u64[0];
  v8->m128i_i64[0] = _mm_blendv_epi8(v12, _mm_packus_epi16(v75, v75), v80).m128i_u64[0];
  a1->m128i_i64[0] = _mm_blendv_epi8(v35, _mm_packus_epi16(v76, v76), v80).m128i_u64[0];
  *(__int64 *)((char *)a1->m128i_i64 + a2) = _mm_blendv_epi8(v36, _mm_packus_epi16(v77, v77), v80).m128i_u64[0];
  *(__int64 *)((char *)a1->m128i_i64 + v13) = _mm_blendv_epi8(v56, _mm_packus_epi16(v78, v78), v80).m128i_u64[0];
  *(__int64 *)((char *)v8->m128i_i64 + v11) = _mm_blendv_epi8(v44, _mm_packus_epi16(v79, v79), v80).m128i_u64[0];
  return result;
}

```

## disassembly

```asm
0x180016e10  mov     rax, rsp
0x180016e13  mov     [rax+8], rbx
0x180016e17  push    rdi
0x180016e18  sub     rsp, 0F0h
0x180016e1f  pmovzxbw xmm0, qword ptr [r8]
0x180016e25  movaps  xmmword ptr [rax-18h], xmm6
0x180016e29  movdqa  xmm1, xmm0
0x180016e2d  movaps  xmmword ptr [rax-28h], xmm7
0x180016e31  paddw   xmm1, xmm0
0x180016e35  movaps  xmmword ptr [rax-38h], xmm8
0x180016e3a  movdqa  xmm4, xmm1
0x180016e3e  movaps  xmmword ptr [rax-48h], xmm9
0x180016e43  paddw   xmm4, xmm1
0x180016e47  movaps  xmmword ptr [rax-58h], xmm10
0x180016e4c  mov     r10, rcx
0x180016e4f  movaps  xmmword ptr [rax-68h], xmm11
0x180016e54  mov     rbx, rcx
0x180016e57  movaps  xmmword ptr [rax-78h], xmm12
0x180016e5c  mov     rdi, rcx
0x180016e5f  lea     eax, ds:0[rdx*4]
0x180016e66  movsxd  r9, edx
0x180016e69  sub     rbx, r9
0x180016e6c  movaps  [rsp+0F8h+var_88], xmm13
0x180016e72  movaps  [rsp+0F8h+var_98], xmm14
0x180016e78  movdqa  xmm2, xmm4
0x180016e7c  paddw   xmm2, xmm1
0x180016e80  movaps  [rsp+0F8h+var_A8], xmm15
0x180016e86  mov     r11, r8
0x180016e89  movsxd  r8, eax
0x180016e8c  movq    xmm15, qword ptr [rbx]
0x180016e91  lea     eax, [rdx+rdx]
0x180016e94  movsxd  rcx, eax
0x180016e97  sub     r10, r8
0x180016e9a  mov     rdx, rbx
0x180016e9d  mov     rax, rdi
0x180016ea0  sub     rdx, rcx
0x180016ea3  sub     rax, rcx
0x180016ea6  movq    xmm3, qword ptr [r10]
0x180016eab  movdqa  [rsp+0F8h+var_D8], xmm3
0x180016eb1  pmovzxbw xmm3, xmm3
0x180016eb6  movdqa  xmm10, xmm3
0x180016ebb  movdqa  xmm6, xmm3
0x180016ebf  paddw   xmm6, xmm0
0x180016ec3  paddw   xmm10, xmm3
0x180016ec8  movq    xmm0, qword ptr [rdx]
0x180016ecc  movdqa  xmm5, xmm10
0x180016ed1  paddw   xmm4, xmm10
0x180016ed6  movdqa  [rsp+0F8h+var_C8], xmm0
0x180016edc  pmovzxbw xmm0, xmm0
0x180016ee1  paddw   xmm5, xmm1
0x180016ee5  movdqa  xmm9, xmm0
0x180016eea  movq    xmm1, qword ptr [rax]
0x180016eee  paddw   xmm9, xmm0
0x180016ef3  paddw   xmm5, xmm9
0x180016ef8  movdqa  [rsp+0F8h+var_B8], xmm1
0x180016efe  movdqa  xmm7, xmm0
0x180016f02  paddw   xmm10, xmm10
0x180016f07  pmovzxbw xmm1, xmm1
0x180016f0c  paddw   xmm10, xmm2
0x180016f11  paddw   xmm6, xmm9
0x180016f16  paddw   xmm10, xmm9
0x180016f1b  paddw   xmm7, xmm3
0x180016f1f  pmovzxbw xmm2, xmm15
0x180016f25  paddw   xmm9, xmm9
0x180016f2a  movdqa  xmm8, xmm1
0x180016f2f  paddw   xmm8, xmm0
0x180016f34  paddw   xmm9, xmm4
0x180016f39  movdqa  xmm0, xmm1
0x180016f3d  paddw   xmm0, xmm1
0x180016f41  movdqa  xmm14, xmm0
0x180016f46  paddw   xmm7, xmm0
0x180016f4a  paddw   xmm14, xmm0
0x180016f4f  paddw   xmm10, xmm0
0x180016f54  paddw   xmm14, xmm5
0x180016f59  paddw   xmm6, xmm0
0x180016f5d  paddw   xmm9, xmm0
0x180016f62  movdqa  xmm5, xmm2
0x180016f66  movdqa  xmm0, xmm2
0x180016f6a  paddw   xmm5, xmm1
0x180016f6e  paddw   xmm0, xmm2
0x180016f72  paddw   xmm10, xmm2
0x180016f77  paddw   xmm8, xmm0
0x180016f7c  paddw   xmm7, xmm0
0x180016f80  paddw   xmm14, xmm0
0x180016f85  movdqa  xmm12, xmm0
0x180016f8a  movq    xmm13, qword ptr [rdi]
0x180016f8f  paddw   xmm9, xmm0
0x180016f94  movq    xmm11, qword ptr [r9+rdi]
0x180016f9a  paddw   xmm12, xmm0
0x180016f9f  paddw   xmm12, xmm6
0x180016fa4  pmovzxbw xmm3, xmm13
0x180016faa  paddw   xmm10, xmm3
0x180016faf  paddw   xmm9, xmm3
0x180016fb4  movdqa  [rsp+0F8h+var_F8], xmm10
0x180016fba  movdqa  xmm4, xmm3
0x180016fbe  paddw   xmm3, xmm3
0x180016fc2  paddw   xmm4, xmm2
0x180016fc6  paddw   xmm5, xmm3
0x180016fca  paddw   xmm12, xmm3
0x180016fcf  paddw   xmm14, xmm3
0x180016fd4  paddw   xmm8, xmm3
0x180016fd9  movdqa  xmm10, xmm3
0x180016fde  paddw   xmm10, xmm3
0x180016fe3  paddw   xmm10, xmm7
0x180016fe8  movq    xmm7, qword ptr [rbx+r8]
0x180016fee  pmovzxbw xmm2, xmm7
0x180016ff3  pmovzxbw xmm1, xmm11
0x180016ff9  paddw   xmm9, xmm1
0x180016ffe  paddw   xmm14, xmm1
0x180017003  movdqa  [rsp+0F8h+var_E8], xmm9
0x18001700a  paddw   xmm1, xmm1
0x18001700e  paddw   xmm5, xmm1
0x180017012  paddw   xmm4, xmm1
0x180017016  paddw   xmm10, xmm1
0x18001701b  paddw   xmm12, xmm1
0x180017020  movdqa  xmm9, xmm1
0x180017025  paddw   xmm9, xmm1
0x18001702a  movdqa  xmm1, cs:xmmword_1800503F0
0x180017032  paddw   xmm9, xmm8
0x180017037  movq    xmm8, qword ptr [rcx+rdi]
0x18001703d  pmovzxbw xmm0, xmm8
0x180017043  paddw   xmm12, xmm0
0x180017048  paddw   xmm14, xmm0
0x18001704d  paddw   xmm0, xmm0
0x180017051  paddw   xmm12, xmm2
0x180017056  paddw   xmm4, xmm0
0x18001705a  paddw   xmm9, xmm0
0x18001705f  paddw   xmm10, xmm0
0x180017064  movdqa  xmm6, xmm0
0x180017068  paddw   xmm6, xmm0
0x18001706c  paddw   xmm10, xmm2
0x180017071  pmovzxbw xmm0, qword ptr [r11+10h]
0x180017078  paddw   xmm6, xmm5
0x18001707c  paddw   xmm10, xmm0
0x180017081  movdqa  xmm5, xmm2
0x180017085  movdqa  xmm3, xmm0
0x180017089  paddw   xmm5, xmm2
0x18001708d  paddw   xmm3, xmm0
0x180017091  paddw   xmm9, xmm5
0x180017096  paddw   xmm6, xmm5
0x18001709a  paddw   xmm5, xmm5
0x18001709e  paddw   xmm9, xmm3
0x1800170a3  paddw   xmm5, xmm4
0x1800170a7  paddw   xmm14, xmm1
0x1800170ac  movdqa  xmm4, [rsp+0F8h+var_F8]
0x1800170b1  paddw   xmm5, xmm3
0x1800170b5  paddw   xmm4, xmm1
0x1800170b9  psrlw   xmm14, 4
0x1800170bf  psrlw   xmm4, 4
0x1800170c4  paddw   xmm3, xmm3
0x1800170c8  movdqa  [rsp+0F8h+var_F8], xmm4
0x1800170cd  paddw   xmm6, xmm3
0x1800170d1  movdqa  xmm4, [rsp+0F8h+var_E8]
0x1800170d7  paddw   xmm5, xmm3
0x1800170db  paddw   xmm4, xmm1
0x1800170df  paddw   xmm12, xmm1
0x1800170e4  paddw   xmm10, xmm1
0x1800170e9  psrlw   xmm4, 4
0x1800170ee  paddw   xmm9, xmm1
0x1800170f3  psrlw   xmm12, 4
0x1800170f9  paddw   xmm6, xmm1
0x1800170fd  psrlw   xmm10, 4
0x180017103  paddw   xmm5, xmm1
0x180017107  psrlw   xmm9, 4
0x18001710d  psrlw   xmm6, 4
0x180017112  psrlw   xmm5, 4
0x180017117  movdqu  xmm0, xmmword ptr [r11+20h]
0x18001711d  lea     r11, [rsp+0F8h+var_8]
0x180017125  movdqa  xmm1, [rsp+0F8h+var_F8]
0x18001712a  movdqa  xmm2, [rsp+0F8h+var_D8]
0x180017130  packuswb xmm1, xmm1
0x180017134  pblendvb xmm2, xmm1
0x180017139  movdqa  xmm1, [rsp+0F8h+var_C8]
0x18001713f  movq    qword ptr [r10], xmm2
0x180017144  packuswb xmm14, xmm14
0x180017149  packuswb xmm12, xmm12
0x18001714e  pblendvb xmm15, xmm12
0x180017154  movaps  xmm12, xmmword ptr [r11-70h]
0x180017159  packuswb xmm10, xmm10
0x18001715e  pblendvb xmm13, xmm10
0x180017164  movaps  xmm10, xmmword ptr [r11-50h]
0x180017169  packuswb xmm9, xmm9
0x18001716e  pblendvb xmm11, xmm9
0x180017174  movaps  xmm9, xmmword ptr [r11-40h]
0x180017179  packuswb xmm6, xmm6
0x18001717d  pblendvb xmm8, xmm6
0x180017183  movaps  xmm6, xmmword ptr [r11-10h]
0x180017188  packuswb xmm4, xmm4
0x18001718c  pblendvb xmm1, xmm4
0x180017191  movq    qword ptr [rdx], xmm1
0x180017195  movdqa  xmm1, [rsp+0F8h+var_B8]
0x18001719b  pblendvb xmm1, xmm14
0x1800171a1  movaps  xmm14, [rsp+0F8h+var_98]
0x1800171a7  movq    qword ptr [rax], xmm1
0x1800171ab  movq    qword ptr [rbx], xmm15
0x1800171b0  movaps  xmm15, [rsp+0F8h+var_A8]
0x1800171b6  movq    qword ptr [rdi], xmm13
0x1800171bb  movaps  xmm13, xmmword ptr [r11-80h]
0x1800171c0  movq    qword ptr [r9+rdi], xmm11
0x1800171c6  movaps  xmm11, xmmword ptr [r11-60h]
0x1800171cb  movq    qword ptr [rcx+rdi], xmm8
0x1800171d1  movaps  xmm8, xmmword ptr [r11-30h]
0x1800171d6  packuswb xmm5, xmm5
0x1800171da  pblendvb xmm7, xmm5
0x1800171df  movq    qword ptr [rbx+r8], xmm7
0x1800171e5  mov     rbx, [r11+10h]
0x1800171e9  movaps  xmm7, xmmword ptr [r11-20h]
0x1800171ee  mov     rsp, r11
0x1800171f1  pop     rdi
0x1800171f2  retn
```
