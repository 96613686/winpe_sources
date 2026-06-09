# m7_ipps_rDftInvRecombine_32f

- ea: `0x1800564a0`
- end: `0x1800565f5`
- name: `m7_ipps_rDftInvRecombine_32f`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180049220`

## callees

- `0x1800564a0`

## pseudocode

```c
__int64 __fastcall m7_ipps_rDftInvRecombine_32f(float *a1, float *a2, __int64 a3, __m128 *a4)
{
  __int64 result; // rax
  float v6; // xmm0_4
  unsigned __int64 v7; // rbp
  float *v8; // r10
  double *v9; // rbp
  float *v10; // r13
  __int64 v11; // rbp
  unsigned __int64 *v12; // r12
  double *v13; // rbx
  __m128 v14; // xmm2
  __m128 v15; // xmm1
  __m128 v16; // xmm0
  __m128 v17; // xmm2
  __m128 v18; // xmm3
  __m128 v19; // xmm4
  __m128 v20; // xmm1
  __m128 v21; // xmm2

  result = a3;
  v6 = *a1 - a1[1];
  *a2 = a1[1] + *a1;
  a2[1] = v6;
  v7 = (a3 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
  v8 = &a1[v7];
  v9 = (double *)&a2[v7];
  if ( (a3 & 1) == 0 )
    _mm_storel_ps(v9, _mm_mul_ps((__m128)*(unsigned __int64 *)v8, (__m128)xmmword_1800B44C0));
  v10 = &a1[2 * a3 - 4];
  v11 = (__int64)&a2[2 * a3 - 4];
  v12 = (unsigned __int64 *)(a1 + 2);
  v13 = (double *)(a2 + 2);
  while ( 1 )
  {
    v14 = _mm_movelh_ps((__m128)*v12, (__m128)v12[1]);
    v15 = _mm_xor_ps(
            _mm_movelh_ps((__m128)*((unsigned __int64 *)v10 + 1), (__m128)*(unsigned __int64 *)v10),
            (__m128)xmmword_1800B44B0);
    v16 = _mm_sub_ps(v14, v15);
    v17 = _mm_add_ps(v14, v15);
    v18 = _mm_mul_ps(_mm_moveldup_ps(*a4), v16);
    v19 = _mm_sub_ps(
            _mm_mul_ps(_mm_movehdup_ps(*a4), v16),
            _mm_xor_ps(_mm_shuffle_ps(v18, v18, 177), (__m128)xmmword_1800B44B0));
    v20 = _mm_add_ps(v17, v19);
    v21 = _mm_sub_ps(_mm_xor_ps(v17, (__m128)xmmword_1800B44B0), _mm_xor_ps(v19, (__m128)xmmword_1800B44B0));
    _mm_storel_ps(v13, v20);
    _mm_storel_ps((double *)(v11 + 8), v21);
    ++a4;
    v12 += 2;
    v10 -= 4;
    v13 += 2;
    v11 -= 16;
    if ( (__int64)v12 >= (__int64)v8 )
      break;
    _mm_storeh_ps(v13 - 1, v20);
    _mm_storeh_ps((double *)(v11 + 16), v21);
  }
  if ( (__int64)v12 <= (__int64)v8 )
  {
    _mm_storeh_ps(v13 - 1, v20);
    _mm_storeh_ps((double *)(v11 + 16), v21);
  }
  return result;
}

```

## disassembly

```asm
0x1800564a0  push    rbx
0x1800564a1  push    rsi
0x1800564a2  push    rdi
0x1800564a3  push    rbp
0x1800564a4  push    r12
0x1800564a6  push    r13
0x1800564a8  sub     rsp, 28h
0x1800564ac  movdqa  [rsp+58h+var_58], xmm7
0x1800564b1  movdqa  [rsp+58h+var_48], xmm6
0x1800564b7  mov     rdi, rcx
0x1800564ba  mov     rsi, rdx
0x1800564bd  mov     rdx, r8
0x1800564c0  mov     rcx, r9
0x1800564c3  mov     r12, rdi
0x1800564c6  mov     rbx, rsi
0x1800564c9  mov     rax, rdx
0x1800564cc  mov     r11, rcx
0x1800564cf  movss   xmm0, dword ptr [r12]
0x1800564d5  movss   xmm1, dword ptr [r12+4]
0x1800564dc  addss   xmm1, xmm0
0x1800564e0  subss   xmm0, dword ptr [r12+4]
0x1800564e7  movss   dword ptr [rbx], xmm1
0x1800564eb  movss   dword ptr [rbx+4], xmm0
0x1800564f0  lea     rbp, [rax+1]
0x1800564f4  and     rbp, 0FFFFFFFFFFFFFFFEh
0x1800564f8  lea     r10, [r12+rbp*4]
0x1800564fc  lea     rbp, [rbx+rbp*4]
0x180056500  test    rax, 1
0x180056506  jnz     short loc_180056518
0x180056508  movsd   xmm0, qword ptr [r10]
0x18005650d  mulps   xmm0, cs:xmmword_1800B44C0
0x180056514  movlps  qword ptr [rbp+0], xmm0
0x180056518  lea     rbp, ds:0[rax*2]
0x180056520  lea     r13, [r12+rbp*4-10h]
0x180056525  lea     rbp, [rbx+rbp*4-10h]
0x18005652a  add     r12, 8
0x18005652e  add     rbx, 8
0x180056532  jmp     short loc_180056548
0x180056540  movhps  qword ptr [rbx-8], xmm1
0x180056544  movhps  qword ptr [rbp+10h], xmm2
0x180056548  movsd   xmm0, qword ptr [r12]
0x18005654e  movsd   xmm7, qword ptr [r12+8]
0x180056555  movlhps xmm0, xmm7
0x180056558  movsd   xmm1, qword ptr [r13+8]
0x18005655e  movsd   xmm7, qword ptr [r13+0]
0x180056564  movlhps xmm1, xmm7
0x180056567  movaps  xmm2, xmm0
0x18005656a  xorps   xmm1, cs:xmmword_1800B44B0
0x180056571  subps   xmm0, xmm1
0x180056574  addps   xmm2, xmm1
0x180056577  movsldup xmm3, xmmword ptr [r11]
0x18005657c  movshdup xmm4, xmmword ptr [r11]
0x180056581  mulps   xmm3, xmm0
0x180056584  mulps   xmm4, xmm0
0x180056587  shufps  xmm3, xmm3, 0B1h
0x18005658b  xorps   xmm3, cs:xmmword_1800B44B0
0x180056592  subps   xmm4, xmm3
0x180056595  movaps  xmm1, xmm2
0x180056598  addps   xmm1, xmm4
0x18005659b  xorps   xmm2, cs:xmmword_1800B44B0
0x1800565a2  xorps   xmm4, cs:xmmword_1800B44B0
0x1800565a9  subps   xmm2, xmm4
0x1800565ac  movlps  qword ptr [rbx], xmm1
0x1800565af  movlps  qword ptr [rbp+8], xmm2
0x1800565b3  add     r11, 10h
0x1800565b7  add     r12, 10h
0x1800565bb  sub     r13, 10h
0x1800565bf  add     rbx, 10h
0x1800565c3  sub     rbp, 10h
0x1800565c7  cmp     r12, r10
0x1800565ca  jl      loc_180056540
0x1800565d0  cmp     r12, r10
0x1800565d3  jg      short loc_1800565DD
0x1800565d5  movhps  qword ptr [rbx-8], xmm1
0x1800565d9  movhps  qword ptr [rbp+10h], xmm2
0x1800565dd  movdqa  xmm7, [rsp+58h+var_58]
0x1800565e2  movdqa  xmm6, [rsp+58h+var_48]
0x1800565e8  add     rsp, 28h
0x1800565ec  pop     r13
0x1800565ee  pop     r12
0x1800565f0  pop     rbp
0x1800565f1  pop     rdi
0x1800565f2  pop     rsi
0x1800565f3  pop     rbx
0x1800565f4  retn
```
