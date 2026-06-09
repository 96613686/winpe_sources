# m7_ipps_rDftFwdRecombine_32f

- ea: `0x180056370`
- end: `0x18005649e`
- name: `m7_ipps_rDftFwdRecombine_32f`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048ab0`

## callees

- `0x180056370`

## pseudocode

```c
__int64 __fastcall m7_ipps_rDftFwdRecombine_32f(float *a1, __int64 a2, __m128 *a3)
{
  __int64 result; // rax
  float v5; // xmm0_4
  float *v6; // r10
  double *v7; // r13
  double *v8; // r12
  __m128 v9; // xmm2
  __m128 v10; // xmm1
  __m128 v11; // xmm0
  __m128 v12; // xmm3
  __m128 v13; // xmm3
  __m128 v14; // xmm1
  __m128 v15; // xmm2

  result = a2;
  v5 = *a1 - a1[1];
  *a1 = a1[1] + *a1;
  a1[1] = v5;
  v6 = &a1[(a2 + 1) & 0xFFFFFFFFFFFFFFFEuLL];
  v7 = (double *)&a1[2 * a2 - 4];
  v8 = (double *)(a1 + 2);
  while ( 1 )
  {
    v9 = _mm_movelh_ps((__m128)*(unsigned __int64 *)v8, (__m128)*((unsigned __int64 *)v8 + 1));
    v10 = _mm_xor_ps(
            _mm_movelh_ps((__m128)*((unsigned __int64 *)v7 + 1), (__m128)*(unsigned __int64 *)v7),
            (__m128)xmmword_1800B44B0);
    v11 = _mm_sub_ps(v9, v10);
    v12 = _mm_mul_ps(_mm_moveldup_ps(*a3), v11);
    v13 = _mm_add_ps(
            _mm_xor_ps(_mm_shuffle_ps(v12, v12, 177), (__m128)xmmword_1800B44B0),
            _mm_mul_ps(_mm_movehdup_ps(*a3), v11));
    v14 = _mm_add_ps(v10, v13);
    v15 = _mm_sub_ps(_mm_xor_ps(v9, (__m128)xmmword_1800B44B0), _mm_xor_ps(v13, (__m128)xmmword_1800B44B0));
    _mm_storel_ps(v8, v14);
    _mm_storel_ps(v7 + 1, v15);
    ++a3;
    v8 += 2;
    v7 -= 2;
    if ( (__int64)v8 >= (__int64)v6 )
      break;
    _mm_storeh_ps(v8 - 1, v14);
    _mm_storeh_ps(v7 + 2, v15);
  }
  if ( (__int64)v8 <= (__int64)v6 )
  {
    _mm_storeh_ps(v8 - 1, v14);
    _mm_storeh_ps(v7 + 2, v15);
  }
  if ( (a2 & 1) == 0 )
    *((_DWORD *)v6 + 1) ^= 0x80000000;
  return result;
}

```

## disassembly

```asm
0x180056370  push    rsi
0x180056371  push    rdi
0x180056372  push    r12
0x180056374  push    r13
0x180056376  sub     rsp, 28h
0x18005637a  movdqa  [rsp+48h+var_48], xmm7
0x18005637f  movdqa  [rsp+48h+var_38], xmm6
0x180056385  mov     rdi, rcx
0x180056388  mov     rsi, rdx
0x18005638b  mov     rdx, r8
0x18005638e  mov     r12, rdi
0x180056391  mov     rax, rsi
0x180056394  mov     r11, rdx
0x180056397  movss   xmm0, dword ptr [r12]
0x18005639d  movss   xmm1, dword ptr [r12+4]
0x1800563a4  addss   xmm1, xmm0
0x1800563a8  subss   xmm0, dword ptr [r12+4]
0x1800563af  movss   dword ptr [r12], xmm1
0x1800563b5  movss   dword ptr [r12+4], xmm0
0x1800563bc  lea     r10, [rax+1]
0x1800563c0  and     r10, 0FFFFFFFFFFFFFFFEh
0x1800563c4  lea     r10, [r12+r10*4]
0x1800563c8  lea     r13, ds:0[rax*2]
0x1800563d0  lea     r13, [r12+r13*4-10h]
0x1800563d5  add     r12, 8
0x1800563d9  jmp     short loc_1800563EB
0x1800563e0  movhps  qword ptr [r12-8], xmm1
0x1800563e6  movhps  qword ptr [r13+10h], xmm2
0x1800563eb  movsd   xmm0, qword ptr [r12]
0x1800563f1  movsd   xmm7, qword ptr [r12+8]
0x1800563f8  movlhps xmm0, xmm7
0x1800563fb  movsd   xmm1, qword ptr [r13+8]
0x180056401  movsd   xmm7, qword ptr [r13+0]
0x180056407  movlhps xmm1, xmm7
0x18005640a  movaps  xmm2, xmm0
0x18005640d  xorps   xmm1, cs:xmmword_1800B44B0
0x180056414  subps   xmm0, xmm1
0x180056417  movsldup xmm3, xmmword ptr [r11]
0x18005641c  movshdup xmm4, xmmword ptr [r11]
0x180056421  mulps   xmm3, xmm0
0x180056424  mulps   xmm4, xmm0
0x180056427  shufps  xmm3, xmm3, 0B1h
0x18005642b  xorps   xmm3, cs:xmmword_1800B44B0
0x180056432  addps   xmm3, xmm4
0x180056435  addps   xmm1, xmm3
0x180056438  xorps   xmm2, cs:xmmword_1800B44B0
0x18005643f  xorps   xmm3, cs:xmmword_1800B44B0
0x180056446  subps   xmm2, xmm3
0x180056449  movlps  qword ptr [r12], xmm1
0x18005644e  movlps  qword ptr [r13+8], xmm2
0x180056453  add     r11, 10h
0x180056457  add     r12, 10h
0x18005645b  sub     r13, 10h
0x18005645f  cmp     r12, r10
0x180056462  jl      loc_1800563E0
0x180056468  cmp     r12, r10
0x18005646b  jg      short loc_180056478
0x18005646d  movhps  qword ptr [r12-8], xmm1
0x180056473  movhps  qword ptr [r13+10h], xmm2
0x180056478  test    rax, 1
0x18005647e  jnz     short loc_180056488
0x180056480  xor     dword ptr [r10+4], 80000000h
0x180056488  movdqa  xmm7, [rsp+48h+var_48]
0x18005648d  movdqa  xmm6, [rsp+48h+var_38]
0x180056493  add     rsp, 28h
0x180056497  pop     r13
0x180056499  pop     r12
0x18005649b  pop     rdi
0x18005649c  pop     rsi
0x18005649d  retn
```
