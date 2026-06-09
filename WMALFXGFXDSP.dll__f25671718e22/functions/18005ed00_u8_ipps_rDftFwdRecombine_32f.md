# u8_ipps_rDftFwdRecombine_32f

- ea: `0x18005ed00`
- end: `0x18005ee2e`
- name: `u8_ipps_rDftFwdRecombine_32f`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e300`

## callees

- `0x18005ed00`

## pseudocode

```c
__int64 __fastcall u8_ipps_rDftFwdRecombine_32f(float *a1, __int64 a2, __m128 *a3)
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
            (__m128)xmmword_1801B72B0);
    v11 = _mm_sub_ps(v9, v10);
    v12 = _mm_mul_ps(_mm_moveldup_ps(*a3), v11);
    v13 = _mm_add_ps(
            _mm_xor_ps(_mm_shuffle_ps(v12, v12, 177), (__m128)xmmword_1801B72B0),
            _mm_mul_ps(_mm_movehdup_ps(*a3), v11));
    v14 = _mm_add_ps(v10, v13);
    v15 = _mm_sub_ps(_mm_xor_ps(v9, (__m128)xmmword_1801B72B0), _mm_xor_ps(v13, (__m128)xmmword_1801B72B0));
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
0x18005ed00  push    rsi
0x18005ed01  push    rdi
0x18005ed02  push    r12
0x18005ed04  push    r13
0x18005ed06  sub     rsp, 28h
0x18005ed0a  movdqa  [rsp+48h+var_48], xmm7
0x18005ed0f  movdqa  [rsp+48h+var_38], xmm6
0x18005ed15  mov     rdi, rcx
0x18005ed18  mov     rsi, rdx
0x18005ed1b  mov     rdx, r8
0x18005ed1e  mov     r12, rdi
0x18005ed21  mov     rax, rsi
0x18005ed24  mov     r11, rdx
0x18005ed27  movss   xmm0, dword ptr [r12]
0x18005ed2d  movss   xmm1, dword ptr [r12+4]
0x18005ed34  addss   xmm1, xmm0
0x18005ed38  subss   xmm0, dword ptr [r12+4]
0x18005ed3f  movss   dword ptr [r12], xmm1
0x18005ed45  movss   dword ptr [r12+4], xmm0
0x18005ed4c  lea     r10, [rax+1]
0x18005ed50  and     r10, 0FFFFFFFFFFFFFFFEh
0x18005ed54  lea     r10, [r12+r10*4]
0x18005ed58  lea     r13, ds:0[rax*2]
0x18005ed60  lea     r13, [r12+r13*4-10h]
0x18005ed65  add     r12, 8
0x18005ed69  jmp     short loc_18005ED7B
0x18005ed70  movhps  qword ptr [r12-8], xmm1
0x18005ed76  movhps  qword ptr [r13+10h], xmm2
0x18005ed7b  movsd   xmm0, qword ptr [r12]
0x18005ed81  movsd   xmm7, qword ptr [r12+8]
0x18005ed88  movlhps xmm0, xmm7
0x18005ed8b  movsd   xmm1, qword ptr [r13+8]
0x18005ed91  movsd   xmm7, qword ptr [r13+0]
0x18005ed97  movlhps xmm1, xmm7
0x18005ed9a  movaps  xmm2, xmm0
0x18005ed9d  xorps   xmm1, cs:xmmword_1801B72B0
0x18005eda4  subps   xmm0, xmm1
0x18005eda7  movsldup xmm3, xmmword ptr [r11]
0x18005edac  movshdup xmm4, xmmword ptr [r11]
0x18005edb1  mulps   xmm3, xmm0
0x18005edb4  mulps   xmm4, xmm0
0x18005edb7  shufps  xmm3, xmm3, 0B1h
0x18005edbb  xorps   xmm3, cs:xmmword_1801B72B0
0x18005edc2  addps   xmm3, xmm4
0x18005edc5  addps   xmm1, xmm3
0x18005edc8  xorps   xmm2, cs:xmmword_1801B72B0
0x18005edcf  xorps   xmm3, cs:xmmword_1801B72B0
0x18005edd6  subps   xmm2, xmm3
0x18005edd9  movlps  qword ptr [r12], xmm1
0x18005edde  movlps  qword ptr [r13+8], xmm2
0x18005ede3  add     r11, 10h
0x18005ede7  add     r12, 10h
0x18005edeb  sub     r13, 10h
0x18005edef  cmp     r12, r10
0x18005edf2  jl      loc_18005ED70
0x18005edf8  cmp     r12, r10
0x18005edfb  jg      short loc_18005EE08
0x18005edfd  movhps  qword ptr [r12-8], xmm1
0x18005ee03  movhps  qword ptr [r13+10h], xmm2
0x18005ee08  test    rax, 1
0x18005ee0e  jnz     short loc_18005EE18
0x18005ee10  xor     dword ptr [r10+4], 80000000h
0x18005ee18  movdqa  xmm7, [rsp+48h+var_48]
0x18005ee1d  movdqa  xmm6, [rsp+48h+var_38]
0x18005ee23  add     rsp, 28h
0x18005ee27  pop     r13
0x18005ee29  pop     r12
0x18005ee2b  pop     rdi
0x18005ee2c  pop     rsi
0x18005ee2d  retn
```
