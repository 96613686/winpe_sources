# u8_ipps_cCcsRecombine_32f

- ea: `0x1800419f0`
- end: `0x180041b4c`
- name: `u8_ipps_cCcsRecombine_32f`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010270`
- `0x180010624`

## callees

- `0x1800419f0`

## pseudocode

```c
void __fastcall u8_ipps_cCcsRecombine_32f(unsigned __int64 *a1, double *a2, __int64 a3, __int64 a4, __m128 *a5)
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
  _mm_storel_ps((double *)((char *)a2 + 4 * a3), _mm_mul_ps((__m128)*v7, (__m128)xmmword_1800B4250));
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
0x1800419f0  push    rbx
0x1800419f1  push    rsi
0x1800419f2  push    rdi
0x1800419f3  push    rbp
0x1800419f4  push    r12
0x1800419f6  push    r13
0x1800419f8  sub     rsp, 28h
0x1800419fc  movdqa  [rsp+58h+var_58], xmm7
0x180041a01  movdqa  [rsp+58h+var_48], xmm6
0x180041a07  mov     rdi, rcx
0x180041a0a  mov     rsi, rdx
0x180041a0d  mov     rdx, r8
0x180041a10  mov     rcx, r9
0x180041a13  mov     r8, [rsp+58h+arg_20]
0x180041a1b  mov     r12, rdi
0x180041a1e  mov     rbx, rsi
0x180041a21  lea     r10, [r12+rdx*4]
0x180041a25  lea     rbp, [rbx+rdx*4]
0x180041a29  movsd   xmm0, qword ptr [r10]
0x180041a2e  mulps   xmm0, cs:xmmword_1800B4250
0x180041a35  movlps  qword ptr [rbp+0], xmm0
0x180041a39  mov     r11, r8
0x180041a3c  lea     r13, [r12+rdx*8]
0x180041a40  lea     rbp, [rbx+rdx*8]
0x180041a44  jmp     short loc_180041A57
0x180041a50  movhps  qword ptr [rbx], xmm0
0x180041a53  movhps  qword ptr [rbp+0], xmm6
0x180041a57  movsd   xmm0, qword ptr [r12+8]
0x180041a5e  movsd   xmm7, qword ptr [r12+10h]
0x180041a65  movlhps xmm0, xmm7
0x180041a68  movaps  xmm1, xmm0
0x180041a6b  movsd   xmm2, qword ptr [r12+18h]
0x180041a72  movsd   xmm7, qword ptr [r12+20h]
0x180041a79  movlhps xmm2, xmm7
0x180041a7c  shufps  xmm0, xmm2, 88h
0x180041a80  shufps  xmm1, xmm2, 0DDh
0x180041a84  movsd   xmm3, qword ptr [r13-8]
0x180041a8a  movsd   xmm7, qword ptr [r13-10h]
0x180041a90  movlhps xmm3, xmm7
0x180041a93  movaps  xmm4, xmm3
0x180041a96  movsd   xmm5, qword ptr [r13-18h]
0x180041a9c  movsd   xmm7, qword ptr [r13-20h]
0x180041aa2  movlhps xmm5, xmm7
0x180041aa5  shufps  xmm3, xmm5, 88h
0x180041aa9  shufps  xmm4, xmm5, 0DDh
0x180041aad  movaps  xmm2, xmm0
0x180041ab0  subps   xmm0, xmm3
0x180041ab3  addps   xmm2, xmm3
0x180041ab6  movaps  xmm5, xmm1
0x180041ab9  addps   xmm5, xmm4
0x180041abc  subps   xmm1, xmm4
0x180041abf  movaps  xmm6, xmmword ptr [r11]
0x180041ac3  mulps   xmm6, xmm0
0x180041ac6  movaps  xmm7, xmmword ptr [r11+10h]
0x180041acb  mulps   xmm0, xmm7
0x180041ace  mulps   xmm7, xmm5
0x180041ad1  mulps   xmm5, xmmword ptr [r11]
0x180041ad5  addps   xmm7, xmm6
0x180041ad8  subps   xmm0, xmm5
0x180041adb  add     r12, 20h ; ' '
0x180041adf  sub     r13, 20h ; ' '
0x180041ae3  movaps  xmm3, xmm2
0x180041ae6  addps   xmm2, xmm0
0x180041ae9  subps   xmm3, xmm0
0x180041aec  movaps  xmm5, xmm1
0x180041aef  addps   xmm1, xmm7
0x180041af2  subps   xmm7, xmm5
0x180041af5  movaps  xmm0, xmm2
0x180041af8  unpcklps xmm2, xmm1
0x180041afb  movlps  qword ptr [rbx+8], xmm2
0x180041aff  movhps  qword ptr [rbx+10h], xmm2
0x180041b03  unpckhps xmm0, xmm1
0x180041b06  movlps  qword ptr [rbx+18h], xmm0
0x180041b0a  add     r11, 20h ; ' '
0x180041b0e  movaps  xmm6, xmm3
0x180041b11  add     rbx, 20h ; ' '
0x180041b15  unpcklps xmm3, xmm7
0x180041b18  movlps  qword ptr [rbp-8], xmm3
0x180041b1c  movhps  qword ptr [rbp-10h], xmm3
0x180041b20  unpckhps xmm6, xmm7
0x180041b23  movlps  qword ptr [rbp-18h], xmm6
0x180041b27  sub     rbp, 20h ; ' '
0x180041b2b  cmp     r12, r10
0x180041b2e  jnz     loc_180041A50
0x180041b34  movdqa  xmm7, [rsp+58h+var_58]
0x180041b39  movdqa  xmm6, [rsp+58h+var_48]
0x180041b3f  add     rsp, 28h
0x180041b43  pop     r13
0x180041b45  pop     r12
0x180041b47  pop     rbp
0x180041b48  pop     rdi
0x180041b49  pop     rsi
0x180041b4a  pop     rbx
0x180041b4b  retn
```
