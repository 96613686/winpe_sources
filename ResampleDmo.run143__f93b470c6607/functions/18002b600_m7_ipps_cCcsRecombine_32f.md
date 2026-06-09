# m7_ipps_cCcsRecombine_32f

- ea: `0x18002b600`
- end: `0x18002b75c`
- name: `m7_ipps_cCcsRecombine_32f`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000efb0`
- `0x18000f364`

## callees

- `0x18002b600`

## pseudocode

```c
void __fastcall m7_ipps_cCcsRecombine_32f(unsigned __int64 *a1, double *a2, __int64 a3, __int64 a4, __m128 *a5)
{
  unsigned __int64 *v5; // r12
  double *v6; // rbx
  unsigned __int64 *v7; // r10
  unsigned __int64 *v9; // r13
  double *i; // rbp
  __m128 v11; // xmm1
  __m128 v12; // xmm2
  __m128 v13; // xmm0
  __m128 v14; // xmm1
  __m128 v15; // xmm4
  __m128 v16; // xmm5
  __m128 v17; // xmm3
  __m128 v18; // xmm4
  __m128 v19; // xmm2
  __m128 v20; // xmm0
  __m128 v21; // xmm5
  __m128 v22; // xmm6
  __m128 v23; // xmm7
  __m128 v24; // xmm0
  __m128 v25; // xmm7
  __m128 v26; // xmm0
  __m128 v27; // xmm3
  __m128 v28; // xmm2
  __m128 v29; // xmm3
  __m128 v30; // xmm5
  __m128 v31; // xmm1
  __m128 v32; // xmm7
  __m128 v33; // xmm0
  __m128 v34; // xmm2
  __m128 v35; // xmm0
  __m128 v36; // xmm6
  __m128 v37; // xmm3
  __m128 v38; // xmm6

  v5 = a1;
  v6 = a2;
  v7 = (unsigned __int64 *)((char *)a1 + 4 * a3);
  _mm_storel_ps((double *)((char *)a2 + 4 * a3), _mm_mul_ps((__m128)*v7, (__m128)xmmword_1800B4110));
  v9 = &a1[a3];
  for ( i = &a2[a3]; ; _mm_storeh_ps(i, v38) )
  {
    v11 = _mm_movelh_ps((__m128)v5[1], (__m128)v5[2]);
    v12 = _mm_movelh_ps((__m128)v5[3], (__m128)v5[4]);
    v13 = _mm_shuffle_ps(v11, v12, 136);
    v14 = _mm_shuffle_ps(v11, v12, 221);
    v15 = _mm_movelh_ps((__m128)*(v9 - 1), (__m128)*(v9 - 2));
    v16 = _mm_movelh_ps((__m128)*(v9 - 3), (__m128)*(v9 - 4));
    v17 = _mm_shuffle_ps(v15, v16, 136);
    v18 = _mm_shuffle_ps(v15, v16, 221);
    v19 = v13;
    v20 = _mm_sub_ps(v13, v17);
    v21 = _mm_add_ps(v14, v18);
    v22 = _mm_mul_ps(*a5, v20);
    v23 = a5[1];
    v24 = _mm_mul_ps(v20, v23);
    v25 = _mm_add_ps(_mm_mul_ps(v23, v21), v22);
    v26 = _mm_sub_ps(v24, _mm_mul_ps(v21, *a5));
    v5 += 4;
    v9 -= 4;
    v27 = _mm_add_ps(v19, v17);
    v28 = _mm_add_ps(v27, v26);
    v29 = _mm_sub_ps(v27, v26);
    v30 = _mm_sub_ps(v14, v18);
    v31 = _mm_add_ps(v30, v25);
    v32 = _mm_sub_ps(v25, v30);
    v33 = v28;
    v34 = _mm_unpacklo_ps(v28, v31);
    _mm_storel_ps(v6 + 1, v34);
    _mm_storeh_ps(v6 + 2, v34);
    v35 = _mm_unpackhi_ps(v33, v31);
    _mm_storel_ps(v6 + 3, v35);
    a5 += 2;
    v36 = v29;
    v6 += 4;
    v37 = _mm_unpacklo_ps(v29, v32);
    _mm_storel_ps(i - 1, v37);
    _mm_storeh_ps(i - 2, v37);
    v38 = _mm_unpackhi_ps(v36, v32);
    _mm_storel_ps(i - 3, v38);
    i -= 4;
    if ( v5 == v7 )
      break;
    _mm_storeh_ps(v6, v35);
  }
}

```

## disassembly

```asm
0x18002b600  push    rbx
0x18002b601  push    rsi
0x18002b602  push    rdi
0x18002b603  push    rbp
0x18002b604  push    r12
0x18002b606  push    r13
0x18002b608  sub     rsp, 28h
0x18002b60c  movdqa  [rsp+58h+var_58], xmm7
0x18002b611  movdqa  [rsp+58h+var_48], xmm6
0x18002b617  mov     rdi, rcx
0x18002b61a  mov     rsi, rdx
0x18002b61d  mov     rdx, r8
0x18002b620  mov     rcx, r9
0x18002b623  mov     r8, [rsp+58h+arg_20]
0x18002b62b  mov     r12, rdi
0x18002b62e  mov     rbx, rsi
0x18002b631  lea     r10, [r12+rdx*4]
0x18002b635  lea     rbp, [rbx+rdx*4]
0x18002b639  movsd   xmm0, qword ptr [r10]
0x18002b63e  mulps   xmm0, cs:xmmword_1800B4110
0x18002b645  movlps  qword ptr [rbp+0], xmm0
0x18002b649  mov     r11, r8
0x18002b64c  lea     r13, [r12+rdx*8]
0x18002b650  lea     rbp, [rbx+rdx*8]
0x18002b654  jmp     short loc_18002B667
0x18002b660  movhps  qword ptr [rbx], xmm0
0x18002b663  movhps  qword ptr [rbp+0], xmm6
0x18002b667  movsd   xmm0, qword ptr [r12+8]
0x18002b66e  movsd   xmm7, qword ptr [r12+10h]
0x18002b675  movlhps xmm0, xmm7
0x18002b678  movaps  xmm1, xmm0
0x18002b67b  movsd   xmm2, qword ptr [r12+18h]
0x18002b682  movsd   xmm7, qword ptr [r12+20h]
0x18002b689  movlhps xmm2, xmm7
0x18002b68c  shufps  xmm0, xmm2, 88h
0x18002b690  shufps  xmm1, xmm2, 0DDh
0x18002b694  movsd   xmm3, qword ptr [r13-8]
0x18002b69a  movsd   xmm7, qword ptr [r13-10h]
0x18002b6a0  movlhps xmm3, xmm7
0x18002b6a3  movaps  xmm4, xmm3
0x18002b6a6  movsd   xmm5, qword ptr [r13-18h]
0x18002b6ac  movsd   xmm7, qword ptr [r13-20h]
0x18002b6b2  movlhps xmm5, xmm7
0x18002b6b5  shufps  xmm3, xmm5, 88h
0x18002b6b9  shufps  xmm4, xmm5, 0DDh
0x18002b6bd  movaps  xmm2, xmm0
0x18002b6c0  subps   xmm0, xmm3
0x18002b6c3  addps   xmm2, xmm3
0x18002b6c6  movaps  xmm5, xmm1
0x18002b6c9  addps   xmm5, xmm4
0x18002b6cc  subps   xmm1, xmm4
0x18002b6cf  movaps  xmm6, xmmword ptr [r11]
0x18002b6d3  mulps   xmm6, xmm0
0x18002b6d6  movaps  xmm7, xmmword ptr [r11+10h]
0x18002b6db  mulps   xmm0, xmm7
0x18002b6de  mulps   xmm7, xmm5
0x18002b6e1  mulps   xmm5, xmmword ptr [r11]
0x18002b6e5  addps   xmm7, xmm6
0x18002b6e8  subps   xmm0, xmm5
0x18002b6eb  add     r12, 20h ; ' '
0x18002b6ef  sub     r13, 20h ; ' '
0x18002b6f3  movaps  xmm3, xmm2
0x18002b6f6  addps   xmm2, xmm0
0x18002b6f9  subps   xmm3, xmm0
0x18002b6fc  movaps  xmm5, xmm1
0x18002b6ff  addps   xmm1, xmm7
0x18002b702  subps   xmm7, xmm5
0x18002b705  movaps  xmm0, xmm2
0x18002b708  unpcklps xmm2, xmm1
0x18002b70b  movlps  qword ptr [rbx+8], xmm2
0x18002b70f  movhps  qword ptr [rbx+10h], xmm2
0x18002b713  unpckhps xmm0, xmm1
0x18002b716  movlps  qword ptr [rbx+18h], xmm0
0x18002b71a  add     r11, 20h ; ' '
0x18002b71e  movaps  xmm6, xmm3
0x18002b721  add     rbx, 20h ; ' '
0x18002b725  unpcklps xmm3, xmm7
0x18002b728  movlps  qword ptr [rbp-8], xmm3
0x18002b72c  movhps  qword ptr [rbp-10h], xmm3
0x18002b730  unpckhps xmm6, xmm7
0x18002b733  movlps  qword ptr [rbp-18h], xmm6
0x18002b737  sub     rbp, 20h ; ' '
0x18002b73b  cmp     r12, r10
0x18002b73e  jnz     loc_18002B660
0x18002b744  movdqa  xmm7, [rsp+58h+var_58]
0x18002b749  movdqa  xmm6, [rsp+58h+var_48]
0x18002b74f  add     rsp, 28h
0x18002b753  pop     r13
0x18002b755  pop     r12
0x18002b757  pop     rbp
0x18002b758  pop     rdi
0x18002b759  pop     rsi
0x18002b75a  pop     rbx
0x18002b75b  retn
```
