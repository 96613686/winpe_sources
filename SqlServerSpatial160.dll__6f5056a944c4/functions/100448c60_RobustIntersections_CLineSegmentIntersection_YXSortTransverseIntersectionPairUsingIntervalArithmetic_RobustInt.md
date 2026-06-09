# RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingIntervalArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x100448c60`
- end: `0x100449060`
- name: `?YXSortTransverseIntersectionPairUsingIntervalArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x100448160`

## callees

- `0x100448c60`
- `0x10044b900`
- `0x10044b9f0`
- `0x10044bc40`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingIntervalArithmetic(
        double *a1)
{
  double v2; // xmm7_8
  __m128d v3; // xmm6
  double v4; // xmm3_8
  double v5; // xmm2_8
  double v6; // xmm1_8
  __int64 v7; // r11
  double v8; // xmm7_8
  __m128d v9; // xmm6
  double *v10; // r11
  double v11; // xmm3_8
  double v12; // xmm2_8
  double v13; // xmm1_8
  unsigned int v14; // r10d
  __int64 v15; // r11
  double v16; // xmm7_8
  __m128d v17; // xmm1
  RobustIntersections::CIntegralInterval *v18; // rax
  const struct RobustIntersections::CIntegralInterval *v19; // r8
  RobustIntersections::CIntegralInterval *v20; // rax
  const struct RobustIntersections::CIntegralInterval *v21; // r8
  unsigned __int64 *v22; // r11
  unsigned int v23; // r10d
  __int64 result; // rax
  __m128d v25; // xmm1
  __m128d v26; // xmm0
  __m128d v27; // xmm1
  RobustIntersections::CIntegralInterval *v28; // rax
  const struct RobustIntersections::CIntegralInterval *v29; // r8
  RobustIntersections::CIntegralInterval *v30; // rax
  const struct RobustIntersections::CIntegralInterval *v31; // r8
  unsigned int v32; // r9d
  double v33; // xmm2_8
  double v34; // xmm5_8
  __m128d v35; // xmm1
  __m128d v36; // xmm0
  __m128d v37; // xmm1
  RobustIntersections::CIntegralInterval *v38; // rax
  const struct RobustIntersections::CIntegralInterval *v39; // r8
  RobustIntersections::CIntegralInterval *v40; // rax
  const struct RobustIntersections::CIntegralInterval *v41; // r8
  __m128d v42; // [rsp+38h] [rbp-79h] BYREF
  double v43; // [rsp+48h] [rbp-69h] BYREF
  double v44; // [rsp+50h] [rbp-61h]
  __m128d v45; // [rsp+58h] [rbp-59h] BYREF
  __m128d v46; // [rsp+68h] [rbp-49h] BYREF
  __m128d v47; // [rsp+78h] [rbp-39h] BYREF
  __m128d v48; // [rsp+88h] [rbp-29h] BYREF
  __m128d v49; // [rsp+98h] [rbp-19h] BYREF
  _BYTE v50[16]; // [rsp+A8h] [rbp-9h] BYREF
  _BYTE v51[16]; // [rsp+B8h] [rbp+7h] BYREF
  __m128d v52; // [rsp+C8h] [rbp+17h] BYREF
  __m128d v53; // [rsp+D8h] [rbp+27h] BYREF

  v2 = a1[3];
  v3 = _mm_unpacklo_pd((__m128d)*((unsigned __int64 *)a1 + 1), (__m128d)*((unsigned __int64 *)a1 + 1));
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v43,
    *a1,
    v3.m128d_f64[0],
    a1[2],
    v2);
  v4 = a1[2];
  v5 = a1[5];
  v6 = a1[4];
  v52 = v3;
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v50,
    v6,
    v5,
    v4,
    v2);
  v8 = *(double *)(v7 + 24);
  v9 = _mm_unpacklo_pd((__m128d)*(unsigned __int64 *)(v7 + 8), (__m128d)*(unsigned __int64 *)(v7 + 8));
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v42,
    *(double *)v7,
    v9.m128d_f64[0],
    *(double *)(v7 + 16),
    v8);
  v11 = v10[2];
  v12 = v10[5];
  v13 = v10[4];
  v53 = v9;
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v51,
    v13,
    v12,
    v11,
    v8);
  RobustIntersections::CIntegralInterval::Multiply(
    (RobustIntersections::CIntegralInterval *)v50,
    (const struct RobustIntersections::CIntegralInterval *)&v42);
  RobustIntersections::CIntegralInterval::Multiply(
    (RobustIntersections::CIntegralInterval *)v51,
    (const struct RobustIntersections::CIntegralInterval *)&v43);
  RobustIntersections::CIntegralInterval::Multiply(
    (RobustIntersections::CIntegralInterval *)&v43,
    (const struct RobustIntersections::CIntegralInterval *)&v42);
  v16 = v44;
  if ( v44 >= 0.0 && v43 <= 0.0 )
    return v14;
  v17 = _mm_unpacklo_pd((__m128d)*(unsigned __int64 *)(v15 + 56), (__m128d)*(unsigned __int64 *)(v15 + 56));
  v47 = _mm_unpacklo_pd((__m128d)*((unsigned __int64 *)a1 + 7), (__m128d)*((unsigned __int64 *)a1 + 7));
  v46 = v17;
  RobustIntersections::CIntegralInterval::Multiply(
    (RobustIntersections::CIntegralInterval *)&v52,
    (const struct RobustIntersections::CIntegralInterval *)v50);
  v18 = RobustIntersections::CIntegralInterval::Multiply(
          (RobustIntersections::CIntegralInterval *)&v47,
          (const struct RobustIntersections::CIntegralInterval *)&v43);
  RobustIntersections::CIntegralInterval::Add(v18, v19);
  RobustIntersections::CIntegralInterval::Multiply(
    (RobustIntersections::CIntegralInterval *)&v53,
    (const struct RobustIntersections::CIntegralInterval *)v51);
  v20 = RobustIntersections::CIntegralInterval::Multiply(
          (RobustIntersections::CIntegralInterval *)&v46,
          (const struct RobustIntersections::CIntegralInterval *)&v43);
  RobustIntersections::CIntegralInterval::Add(v20, v21);
  result = v23;
  if ( v16 >= 0.0 )
  {
    if ( v47.m128d_f64[1] < v46.m128d_f64[0] || v46.m128d_f64[1] < v47.m128d_f64[0] )
    {
      result = 1;
      if ( v46.m128d_f64[0] > v47.m128d_f64[1] )
        result = 0xFFFFFFFFLL;
    }
    else if ( v47.m128d_f64[0] == v46.m128d_f64[0]
           && v47.m128d_f64[1] == v46.m128d_f64[1]
           && v47.m128d_f64[1] == v47.m128d_f64[0] )
    {
      result = 0;
    }
    if ( !(_DWORD)result )
    {
      v35 = _mm_unpacklo_pd((__m128d)*((unsigned __int64 *)a1 + 6), (__m128d)*((unsigned __int64 *)a1 + 6));
      v49 = _mm_unpacklo_pd((__m128d)*(unsigned __int64 *)a1, (__m128d)*(unsigned __int64 *)a1);
      v36 = (__m128d)*v22;
      v45 = v35;
      v37 = _mm_unpacklo_pd((__m128d)v22[6], (__m128d)v22[6]);
      v48 = _mm_unpacklo_pd(v36, v36);
      v42 = v37;
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)&v49,
        (const struct RobustIntersections::CIntegralInterval *)v50);
      v38 = RobustIntersections::CIntegralInterval::Multiply(
              (RobustIntersections::CIntegralInterval *)&v45,
              (const struct RobustIntersections::CIntegralInterval *)&v43);
      RobustIntersections::CIntegralInterval::Add(v38, v39);
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)&v48,
        (const struct RobustIntersections::CIntegralInterval *)v51);
      v40 = RobustIntersections::CIntegralInterval::Multiply(
              (RobustIntersections::CIntegralInterval *)&v42,
              (const struct RobustIntersections::CIntegralInterval *)&v43);
      RobustIntersections::CIntegralInterval::Add(v40, v41);
      v33 = v42.m128d_f64[0];
      v34 = v45.m128d_f64[1];
      if ( v45.m128d_f64[1] >= v42.m128d_f64[0] && v42.m128d_f64[1] >= v45.m128d_f64[0] )
      {
        if ( v45.m128d_f64[0] == v42.m128d_f64[0]
          && v45.m128d_f64[1] == v42.m128d_f64[1]
          && v45.m128d_f64[1] == v45.m128d_f64[0] )
        {
          return 0;
        }
        return v14;
      }
      goto LABEL_34;
    }
  }
  else
  {
    if ( v46.m128d_f64[1] < v47.m128d_f64[0] || v47.m128d_f64[1] < v46.m128d_f64[0] )
    {
      result = 1;
      if ( v47.m128d_f64[0] > v46.m128d_f64[1] )
        result = 0xFFFFFFFFLL;
    }
    else if ( v46.m128d_f64[0] == v47.m128d_f64[0]
           && v46.m128d_f64[1] == v47.m128d_f64[1]
           && v46.m128d_f64[1] == v46.m128d_f64[0] )
    {
      result = 0;
    }
    if ( !(_DWORD)result )
    {
      v25 = _mm_unpacklo_pd((__m128d)*((unsigned __int64 *)a1 + 6), (__m128d)*((unsigned __int64 *)a1 + 6));
      v48 = _mm_unpacklo_pd((__m128d)*(unsigned __int64 *)a1, (__m128d)*(unsigned __int64 *)a1);
      v26 = (__m128d)*v22;
      v45 = v25;
      v27 = _mm_unpacklo_pd((__m128d)v22[6], (__m128d)v22[6]);
      v49 = _mm_unpacklo_pd(v26, v26);
      v42 = v27;
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)&v48,
        (const struct RobustIntersections::CIntegralInterval *)v50);
      v28 = RobustIntersections::CIntegralInterval::Multiply(
              (RobustIntersections::CIntegralInterval *)&v45,
              (const struct RobustIntersections::CIntegralInterval *)&v43);
      RobustIntersections::CIntegralInterval::Add(v28, v29);
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)&v49,
        (const struct RobustIntersections::CIntegralInterval *)v51);
      v30 = RobustIntersections::CIntegralInterval::Multiply(
              (RobustIntersections::CIntegralInterval *)&v42,
              (const struct RobustIntersections::CIntegralInterval *)&v43);
      RobustIntersections::CIntegralInterval::Add(v30, v31);
      v33 = v45.m128d_f64[0];
      v34 = v42.m128d_f64[1];
      if ( v42.m128d_f64[1] >= v45.m128d_f64[0] && v45.m128d_f64[1] >= v42.m128d_f64[0] )
      {
        if ( v42.m128d_f64[0] == v45.m128d_f64[0]
          && v42.m128d_f64[1] == v45.m128d_f64[1]
          && v42.m128d_f64[1] == v42.m128d_f64[0] )
        {
          return 0;
        }
        return v14;
      }
LABEL_34:
      v14 = 1;
      if ( v33 > v34 )
        return v32;
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100448c60  mov     rax, rsp
0x100448c63  mov     [rax+8], rbx
0x100448c67  push    rbp
0x100448c68  lea     rbp, [rax-5Fh]
0x100448c6c  sub     rsp, 100h
0x100448c73  movsd   xmm3, qword ptr [rcx+10h]; double
0x100448c78  mov     rbx, rcx
0x100448c7b  movsd   xmm1, qword ptr [rcx]; double
0x100448c7f  mov     r11, rdx
0x100448c82  movaps  xmmword ptr [rax-18h], xmm6
0x100448c86  mov     r10d, 80000000h
0x100448c8c  movsd   xmm6, qword ptr [rcx+8]
0x100448c91  movaps  xmmword ptr [rax-28h], xmm7
0x100448c95  movsd   xmm7, qword ptr [rcx+18h]
0x100448c9a  lea     rcx, [rbp+57h+var_C0]; this
0x100448c9e  unpcklpd xmm6, xmm6
0x100448ca2  movaps  xmm2, xmm6; double
0x100448ca5  movsd   [rsp+100h+var_E0], xmm7; double
0x100448cab  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100448cb0  movsd   xmm3, qword ptr [rbx+10h]; double
0x100448cb5  lea     rcx, [rbp+57h+var_60]; this
0x100448cb9  movsd   xmm2, qword ptr [rbx+28h]; double
0x100448cbe  movsd   xmm1, qword ptr [rbx+20h]; double
0x100448cc3  movsd   [rsp+100h+var_E0], xmm7; double
0x100448cc9  movups  [rbp+57h+var_40], xmm6
0x100448ccd  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100448cd2  movsd   xmm6, qword ptr [r11+8]
0x100448cd8  lea     rcx, [rbp+57h+var_D0]; this
0x100448cdc  movsd   xmm7, qword ptr [r11+18h]
0x100448ce2  movsd   xmm3, qword ptr [r11+10h]; double
0x100448ce8  movsd   xmm1, qword ptr [r11]; double
0x100448ced  unpcklpd xmm6, xmm6
0x100448cf1  movaps  xmm2, xmm6; double
0x100448cf4  movsd   [rsp+100h+var_E0], xmm7; double
0x100448cfa  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100448cff  movsd   xmm3, qword ptr [r11+10h]; double
0x100448d05  lea     rcx, [rbp+57h+var_50]; this
0x100448d09  movsd   xmm2, qword ptr [r11+28h]; double
0x100448d0f  movsd   xmm1, qword ptr [r11+20h]; double
0x100448d15  movsd   [rsp+100h+var_E0], xmm7; double
0x100448d1b  movups  [rbp+57h+var_30], xmm6
0x100448d1f  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100448d24  lea     rdx, [rbp+57h+var_D0]; struct RobustIntersections::CIntegralInterval *
0x100448d28  lea     rcx, [rbp+57h+var_60]; this
0x100448d2c  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448d31  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448d35  lea     rcx, [rbp+57h+var_50]; this
0x100448d39  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448d3e  lea     rdx, [rbp+57h+var_D0]; struct RobustIntersections::CIntegralInterval *
0x100448d42  lea     rcx, [rbp+57h+var_C0]; this
0x100448d46  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448d4b  movsd   xmm7, [rbp+57h+var_B8]
0x100448d50  xorps   xmm6, xmm6
0x100448d53  comisd  xmm6, xmm7
0x100448d57  ja      short loc_100448D6F
0x100448d59  movsd   xmm0, [rbp+57h+var_C0]
0x100448d5e  xor     eax, eax
0x100448d60  comisd  xmm0, xmm6
0x100448d64  setnbe  al
0x100448d67  test    eax, eax
0x100448d69  jz      loc_100449042
0x100448d6f  movsd   xmm0, qword ptr [rbx+38h]
0x100448d74  lea     rdx, [rbp+57h+var_60]; struct RobustIntersections::CIntegralInterval *
0x100448d78  movsd   xmm1, qword ptr [r11+38h]
0x100448d7e  lea     rcx, [rbp+57h+var_40]; this
0x100448d82  unpcklpd xmm0, xmm0
0x100448d86  unpcklpd xmm1, xmm1
0x100448d8a  movups  [rbp+57h+var_90], xmm0
0x100448d8e  movups  [rbp+57h+var_A0], xmm1
0x100448d92  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448d97  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448d9b  mov     r8, rax
0x100448d9e  lea     rcx, [rbp+57h+var_90]; this
0x100448da2  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448da7  mov     rcx, rax; this
0x100448daa  mov     rdx, r8; struct RobustIntersections::CIntegralInterval *
0x100448dad  call    ?Add@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Add(RobustIntersections::CIntegralInterval const &)
0x100448db2  lea     rdx, [rbp+57h+var_50]; struct RobustIntersections::CIntegralInterval *
0x100448db6  lea     rcx, [rbp+57h+var_30]; this
0x100448dba  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448dbf  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448dc3  mov     r8, rax
0x100448dc6  lea     rcx, [rbp+57h+var_A0]; this
0x100448dca  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448dcf  mov     rcx, rax; this
0x100448dd2  mov     rdx, r8; struct RobustIntersections::CIntegralInterval *
0x100448dd5  call    ?Add@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Add(RobustIntersections::CIntegralInterval const &)
0x100448dda  comisd  xmm6, xmm7
0x100448dde  mov     eax, r10d
0x100448de1  mov     r9d, 0FFFFFFFFh
0x100448de7  jbe     loc_100448F22
0x100448ded  movsd   xmm0, qword ptr [rbp+57h+var_A0+8]
0x100448df2  movsd   xmm1, qword ptr [rbp+57h+var_90]
0x100448df7  comisd  xmm0, xmm1
0x100448dfb  jb      short loc_100448E29
0x100448dfd  movsd   xmm3, qword ptr [rbp+57h+var_90+8]
0x100448e02  movsd   xmm2, qword ptr [rbp+57h+var_A0]
0x100448e07  comisd  xmm3, xmm2
0x100448e0b  jb      short loc_100448E29
0x100448e0d  ucomisd xmm2, xmm1
0x100448e11  jp      short loc_100448E36
0x100448e13  jnz     short loc_100448E36
0x100448e15  ucomisd xmm0, xmm3
0x100448e19  jp      short loc_100448E36
0x100448e1b  jnz     short loc_100448E36
0x100448e1d  ucomisd xmm0, xmm2
0x100448e21  jp      short loc_100448E36
0x100448e23  jnz     short loc_100448E36
0x100448e25  xor     eax, eax
0x100448e27  jmp     short loc_100448E36
0x100448e29  comisd  xmm1, xmm0
0x100448e2d  mov     eax, 1
0x100448e32  cmova   eax, r9d
0x100448e36  test    eax, eax
0x100448e38  jnz     loc_100449045
0x100448e3e  movsd   xmm0, qword ptr [rbx]
0x100448e42  lea     rdx, [rbp+57h+var_60]; struct RobustIntersections::CIntegralInterval *
0x100448e46  movsd   xmm1, qword ptr [rbx+30h]
0x100448e4b  lea     rcx, [rbp+57h+var_80]; this
0x100448e4f  unpcklpd xmm0, xmm0
0x100448e53  unpcklpd xmm1, xmm1
0x100448e57  movups  [rbp+57h+var_80], xmm0
0x100448e5b  movsd   xmm0, qword ptr [r11]
0x100448e60  movups  [rbp+57h+var_B0], xmm1
0x100448e64  movsd   xmm1, qword ptr [r11+30h]
0x100448e6a  unpcklpd xmm0, xmm0
0x100448e6e  unpcklpd xmm1, xmm1
0x100448e72  movups  [rbp+57h+var_70], xmm0
0x100448e76  movups  [rbp+57h+var_D0], xmm1
0x100448e7a  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448e7f  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448e83  mov     r8, rax
0x100448e86  lea     rcx, [rbp+57h+var_B0]; this
0x100448e8a  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448e8f  mov     rcx, rax; this
0x100448e92  mov     rdx, r8; struct RobustIntersections::CIntegralInterval *
0x100448e95  call    ?Add@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Add(RobustIntersections::CIntegralInterval const &)
0x100448e9a  lea     rdx, [rbp+57h+var_50]; struct RobustIntersections::CIntegralInterval *
0x100448e9e  lea     rcx, [rbp+57h+var_70]; this
0x100448ea2  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448ea7  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448eab  mov     r8, rax
0x100448eae  lea     rcx, [rbp+57h+var_D0]; this
0x100448eb2  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448eb7  mov     rcx, rax; this
0x100448eba  mov     rdx, r8; struct RobustIntersections::CIntegralInterval *
0x100448ebd  call    ?Add@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Add(RobustIntersections::CIntegralInterval const &)
0x100448ec2  movsd   xmm2, qword ptr [rbp+57h+var_B0]
0x100448ec7  movsd   xmm5, qword ptr [rbp+57h+var_D0+8]
0x100448ecc  comisd  xmm5, xmm2
0x100448ed0  jb      loc_100449034
0x100448ed6  movsd   xmm1, qword ptr [rbp+57h+var_B0+8]
0x100448edb  movsd   xmm0, qword ptr [rbp+57h+var_D0]
0x100448ee0  comisd  xmm1, xmm0
0x100448ee4  jb      loc_100449034
0x100448eea  ucomisd xmm0, xmm2
0x100448eee  jp      loc_100449042
0x100448ef4  jnz     loc_100449042
0x100448efa  ucomisd xmm5, xmm1
0x100448efe  jp      loc_100449042
0x100448f04  jnz     loc_100449042
0x100448f0a  ucomisd xmm5, xmm0
0x100448f0e  jp      loc_100449042
0x100448f14  jnz     loc_100449042
0x100448f1a  xor     r10d, r10d
0x100448f1d  jmp     loc_100449042
0x100448f22  movsd   xmm0, qword ptr [rbp+57h+var_90+8]
0x100448f27  movsd   xmm1, qword ptr [rbp+57h+var_A0]
0x100448f2c  comisd  xmm0, xmm1
0x100448f30  jb      short loc_100448F5E
0x100448f32  movsd   xmm3, qword ptr [rbp+57h+var_A0+8]
0x100448f37  movsd   xmm2, qword ptr [rbp+57h+var_90]
0x100448f3c  comisd  xmm3, xmm2
0x100448f40  jb      short loc_100448F5E
0x100448f42  ucomisd xmm2, xmm1
0x100448f46  jp      short loc_100448F6B
0x100448f48  jnz     short loc_100448F6B
0x100448f4a  ucomisd xmm0, xmm3
0x100448f4e  jp      short loc_100448F6B
0x100448f50  jnz     short loc_100448F6B
0x100448f52  ucomisd xmm0, xmm2
0x100448f56  jp      short loc_100448F6B
0x100448f58  jnz     short loc_100448F6B
0x100448f5a  xor     eax, eax
0x100448f5c  jmp     short loc_100448F6B
0x100448f5e  comisd  xmm1, xmm0
0x100448f62  mov     eax, 1
0x100448f67  cmova   eax, r9d
0x100448f6b  test    eax, eax
0x100448f6d  jnz     loc_100449045
0x100448f73  movsd   xmm0, qword ptr [rbx]
0x100448f77  lea     rdx, [rbp+57h+var_60]; struct RobustIntersections::CIntegralInterval *
0x100448f7b  movsd   xmm1, qword ptr [rbx+30h]
0x100448f80  lea     rcx, [rbp+57h+var_70]; this
0x100448f84  unpcklpd xmm0, xmm0
0x100448f88  unpcklpd xmm1, xmm1
0x100448f8c  movups  [rbp+57h+var_70], xmm0
0x100448f90  movsd   xmm0, qword ptr [r11]
0x100448f95  movups  [rbp+57h+var_B0], xmm1
0x100448f99  movsd   xmm1, qword ptr [r11+30h]
0x100448f9f  unpcklpd xmm0, xmm0
0x100448fa3  unpcklpd xmm1, xmm1
0x100448fa7  movups  [rbp+57h+var_80], xmm0
0x100448fab  movups  [rbp+57h+var_D0], xmm1
0x100448faf  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448fb4  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448fb8  mov     r8, rax
0x100448fbb  lea     rcx, [rbp+57h+var_B0]; this
0x100448fbf  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448fc4  mov     rcx, rax; this
0x100448fc7  mov     rdx, r8; struct RobustIntersections::CIntegralInterval *
0x100448fca  call    ?Add@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Add(RobustIntersections::CIntegralInterval const &)
0x100448fcf  lea     rdx, [rbp+57h+var_50]; struct RobustIntersections::CIntegralInterval *
0x100448fd3  lea     rcx, [rbp+57h+var_80]; this
0x100448fd7  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448fdc  lea     rdx, [rbp+57h+var_C0]; struct RobustIntersections::CIntegralInterval *
0x100448fe0  mov     r8, rax
0x100448fe3  lea     rcx, [rbp+57h+var_D0]; this
0x100448fe7  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100448fec  mov     rcx, rax; this
0x100448fef  mov     rdx, r8; struct RobustIntersections::CIntegralInterval *
0x100448ff2  call    ?Add@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Add(RobustIntersections::CIntegralInterval const &)
0x100448ff7  movsd   xmm2, qword ptr [rbp+57h+var_D0]
0x100448ffc  movsd   xmm5, qword ptr [rbp+57h+var_B0+8]
0x100449001  comisd  xmm5, xmm2
0x100449005  jb      short loc_100449034
0x100449007  movsd   xmm1, qword ptr [rbp+57h+var_D0+8]
0x10044900c  movsd   xmm0, qword ptr [rbp+57h+var_B0]
0x100449011  comisd  xmm1, xmm0
0x100449015  jb      short loc_100449034
0x100449017  ucomisd xmm0, xmm2
0x10044901b  jp      short loc_100449042
0x10044901d  jnz     short loc_100449042
0x10044901f  ucomisd xmm5, xmm1
0x100449023  jp      short loc_100449042
0x100449025  jnz     short loc_100449042
0x100449027  ucomisd xmm5, xmm0
0x10044902b  jp      short loc_100449042
0x10044902d  jnz     short loc_100449042
0x10044902f  xor     r10d, r10d
0x100449032  jmp     short loc_100449042
0x100449034  comisd  xmm2, xmm5
0x100449038  mov     r10d, 1
0x10044903e  cmova   r10d, r9d
0x100449042  mov     eax, r10d
0x100449045  lea     r11, [rsp+100h+var_s0]
0x10044904d  mov     rbx, [r11+10h]
0x100449051  movaps  xmm6, xmmword ptr [r11-10h]
0x100449056  movaps  xmm7, xmmword ptr [r11-20h]
0x10044905b  mov     rsp, r11
0x10044905e  pop     rbp
0x10044905f  retn
```
