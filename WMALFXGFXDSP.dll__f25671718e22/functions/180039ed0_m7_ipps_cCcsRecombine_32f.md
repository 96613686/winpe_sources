# m7_ipps_cCcsRecombine_32f

- ea: `0x180039ed0`
- end: `0x18003a02c`
- name: `m7_ipps_cCcsRecombine_32f`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a6e0`
- `0x18001aa94`

## callees

- `0x180039ed0`

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
  _mm_storel_ps((double *)((char *)a2 + 4 * a3), _mm_mul_ps((__m128)*v7, (__m128)xmmword_1801B70D0));
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
0x180039ed0  push    rbx
0x180039ed1  push    rsi
0x180039ed2  push    rdi
0x180039ed3  push    rbp
0x180039ed4  push    r12
0x180039ed6  push    r13
0x180039ed8  sub     rsp, 28h
0x180039edc  movdqa  [rsp+58h+var_58], xmm7
0x180039ee1  movdqa  [rsp+58h+var_48], xmm6
0x180039ee7  mov     rdi, rcx
0x180039eea  mov     rsi, rdx
0x180039eed  mov     rdx, r8
0x180039ef0  mov     rcx, r9
0x180039ef3  mov     r8, [rsp+58h+arg_20]
0x180039efb  mov     r12, rdi
0x180039efe  mov     rbx, rsi
0x180039f01  lea     r10, [r12+rdx*4]
0x180039f05  lea     rbp, [rbx+rdx*4]
0x180039f09  movsd   xmm0, qword ptr [r10]
0x180039f0e  mulps   xmm0, cs:xmmword_1801B70D0
0x180039f15  movlps  qword ptr [rbp+0], xmm0
0x180039f19  mov     r11, r8
0x180039f1c  lea     r13, [r12+rdx*8]
0x180039f20  lea     rbp, [rbx+rdx*8]
0x180039f24  jmp     short loc_180039F37
0x180039f30  movhps  qword ptr [rbx], xmm0
0x180039f33  movhps  qword ptr [rbp+0], xmm6
0x180039f37  movsd   xmm0, qword ptr [r12+8]
0x180039f3e  movsd   xmm7, qword ptr [r12+10h]
0x180039f45  movlhps xmm0, xmm7
0x180039f48  movaps  xmm1, xmm0
0x180039f4b  movsd   xmm2, qword ptr [r12+18h]
0x180039f52  movsd   xmm7, qword ptr [r12+20h]
0x180039f59  movlhps xmm2, xmm7
0x180039f5c  shufps  xmm0, xmm2, 88h
0x180039f60  shufps  xmm1, xmm2, 0DDh
0x180039f64  movsd   xmm3, qword ptr [r13-8]
0x180039f6a  movsd   xmm7, qword ptr [r13-10h]
0x180039f70  movlhps xmm3, xmm7
0x180039f73  movaps  xmm4, xmm3
0x180039f76  movsd   xmm5, qword ptr [r13-18h]
0x180039f7c  movsd   xmm7, qword ptr [r13-20h]
0x180039f82  movlhps xmm5, xmm7
0x180039f85  shufps  xmm3, xmm5, 88h
0x180039f89  shufps  xmm4, xmm5, 0DDh
0x180039f8d  movaps  xmm2, xmm0
0x180039f90  subps   xmm0, xmm3
0x180039f93  addps   xmm2, xmm3
0x180039f96  movaps  xmm5, xmm1
0x180039f99  addps   xmm5, xmm4
0x180039f9c  subps   xmm1, xmm4
0x180039f9f  movaps  xmm6, xmmword ptr [r11]
0x180039fa3  mulps   xmm6, xmm0
0x180039fa6  movaps  xmm7, xmmword ptr [r11+10h]
0x180039fab  mulps   xmm0, xmm7
0x180039fae  mulps   xmm7, xmm5
0x180039fb1  mulps   xmm5, xmmword ptr [r11]
0x180039fb5  addps   xmm7, xmm6
0x180039fb8  subps   xmm0, xmm5
0x180039fbb  add     r12, 20h ; ' '
0x180039fbf  sub     r13, 20h ; ' '
0x180039fc3  movaps  xmm3, xmm2
0x180039fc6  addps   xmm2, xmm0
0x180039fc9  subps   xmm3, xmm0
0x180039fcc  movaps  xmm5, xmm1
0x180039fcf  addps   xmm1, xmm7
0x180039fd2  subps   xmm7, xmm5
0x180039fd5  movaps  xmm0, xmm2
0x180039fd8  unpcklps xmm2, xmm1
0x180039fdb  movlps  qword ptr [rbx+8], xmm2
0x180039fdf  movhps  qword ptr [rbx+10h], xmm2
0x180039fe3  unpckhps xmm0, xmm1
0x180039fe6  movlps  qword ptr [rbx+18h], xmm0
0x180039fea  add     r11, 20h ; ' '
0x180039fee  movaps  xmm6, xmm3
0x180039ff1  add     rbx, 20h ; ' '
0x180039ff5  unpcklps xmm3, xmm7
0x180039ff8  movlps  qword ptr [rbp-8], xmm3
0x180039ffc  movhps  qword ptr [rbp-10h], xmm3
0x18003a000  unpckhps xmm6, xmm7
0x18003a003  movlps  qword ptr [rbp-18h], xmm6
0x18003a007  sub     rbp, 20h ; ' '
0x18003a00b  cmp     r12, r10
0x18003a00e  jnz     loc_180039F30
0x18003a014  movdqa  xmm7, [rsp+58h+var_58]
0x18003a019  movdqa  xmm6, [rsp+58h+var_48]
0x18003a01f  add     rsp, 28h
0x18003a023  pop     r13
0x18003a025  pop     r12
0x18003a027  pop     rbp
0x18003a028  pop     rdi
0x18003a029  pop     rsi
0x18003a02a  pop     rbx
0x18003a02b  retn
```
