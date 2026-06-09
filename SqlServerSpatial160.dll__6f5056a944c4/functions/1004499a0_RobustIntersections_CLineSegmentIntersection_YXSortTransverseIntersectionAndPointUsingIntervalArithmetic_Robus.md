# RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingIntervalArithmetic(RobustIntersections::CLineSegmentIntersection const &,double const * const,bool)

- ea: `0x1004499a0`
- end: `0x100449bfb`
- name: `?YXSortTransverseIntersectionAndPointUsingIntervalArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@QEBN_N@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100448310`

## callees

- `0x1004499a0`
- `0x10044b9f0`
- `0x10044bc40`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionAndPointUsingIntervalArithmetic(
        double *a1,
        unsigned __int64 *a2)
{
  double v3; // xmm7_8
  __m128d v4; // xmm12
  __m128d v5; // xmm9
  unsigned int v6; // r10d
  double *v7; // r11
  double v8; // xmm10_8
  char v10; // r8
  unsigned int v11; // r10d
  __int64 v12; // r11
  __m128d v13; // xmm0
  unsigned int v14; // r9d
  unsigned int v15; // r10d
  unsigned int v16; // ecx
  int v17; // eax
  __m128d v18; // xmm0
  unsigned int v19; // r9d
  double v20; // xmm0_8
  double v21; // xmm2_8
  double v22; // xmm3_8
  double v23; // xmm1_8
  double v24; // [rsp+38h] [rbp-39h] BYREF
  double v25; // [rsp+40h] [rbp-31h]
  __m128d v26; // [rsp+48h] [rbp-29h] BYREF
  __m128d v27; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v28[96]; // [rsp+68h] [rbp-9h] BYREF

  v3 = a1[3];
  v4 = _mm_unpacklo_pd((__m128d)*(unsigned __int64 *)a1, (__m128d)*(unsigned __int64 *)a1);
  v5 = _mm_unpacklo_pd((__m128d)*((unsigned __int64 *)a1 + 1), (__m128d)*((unsigned __int64 *)a1 + 1));
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v24,
    v4.m128d_f64[0],
    v5.m128d_f64[0],
    a1[2],
    v3);
  v8 = v24;
  if ( v25 >= 0.0 && v24 <= 0.0 )
    return v6;
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v28,
    v7[4],
    v7[5],
    v7[2],
    v3);
  if ( !v10 )
  {
    v13 = (__m128d)a2[1];
    v13.m128d_f64[0] = v13.m128d_f64[0] - *(double *)(v12 + 56);
    v26 = v5;
    v27 = _mm_unpacklo_pd(v13, v13);
    RobustIntersections::CIntegralInterval::Multiply(
      (RobustIntersections::CIntegralInterval *)&v27,
      (const struct RobustIntersections::CIntegralInterval *)&v24);
    RobustIntersections::CIntegralInterval::Multiply(
      (RobustIntersections::CIntegralInterval *)&v26,
      (const struct RobustIntersections::CIntegralInterval *)v28);
    v16 = v15;
    if ( v26.m128d_f64[1] < v27.m128d_f64[0] || v27.m128d_f64[1] < v26.m128d_f64[0] )
    {
      v16 = v14;
      if ( v27.m128d_f64[0] > v26.m128d_f64[1] )
        v16 = -1;
    }
    else if ( v26.m128d_f64[0] == v27.m128d_f64[0]
           && v26.m128d_f64[1] == v27.m128d_f64[1]
           && v26.m128d_f64[1] == v26.m128d_f64[0] )
    {
      v16 = 0;
    }
    if ( ((v16 + 1) & 0xFFFFFFFD) == 0 && v25 < 0.0 )
    {
      v17 = -1;
      if ( v16 == -1 )
        v17 = v14;
      v16 = v17;
    }
    if ( v16 )
      return v16;
LABEL_21:
    v18 = (__m128d)*a2;
    v18.m128d_f64[0] = v18.m128d_f64[0] - *(double *)(v12 + 48);
    v26 = v4;
    v27 = _mm_unpacklo_pd(v18, v18);
    RobustIntersections::CIntegralInterval::Multiply(
      (RobustIntersections::CIntegralInterval *)&v27,
      (const struct RobustIntersections::CIntegralInterval *)&v24);
    RobustIntersections::CIntegralInterval::Multiply(
      (RobustIntersections::CIntegralInterval *)&v26,
      (const struct RobustIntersections::CIntegralInterval *)v28);
    if ( v25 >= 0.0 && v8 > 0.0 == v19 )
    {
      v20 = v26.m128d_f64[1];
      v21 = v27.m128d_f64[0];
      if ( v26.m128d_f64[1] >= v27.m128d_f64[0] )
      {
        v22 = v27.m128d_f64[1];
        v23 = v26.m128d_f64[0];
        if ( v27.m128d_f64[1] >= v26.m128d_f64[0] )
          goto LABEL_25;
      }
    }
    else
    {
      v20 = v27.m128d_f64[1];
      v21 = v26.m128d_f64[0];
      if ( v27.m128d_f64[1] >= v26.m128d_f64[0] )
      {
        v22 = v26.m128d_f64[1];
        v23 = v27.m128d_f64[0];
        if ( v26.m128d_f64[1] >= v27.m128d_f64[0] )
        {
LABEL_25:
          if ( v23 == v21 && v20 == v22 && v20 == v23 )
            return 0;
          return v11;
        }
      }
    }
    v11 = v19;
    if ( v21 > v20 )
      return (unsigned int)-1;
    return v11;
  }
  if ( v10 == 1 )
    goto LABEL_21;
  return v11;
}

```

## disassembly

```asm
0x1004499a0  mov     rax, rsp
0x1004499a3  mov     [rax+10h], rbx
0x1004499a7  push    rbp
0x1004499a8  lea     rbp, [rax-5Fh]
0x1004499ac  sub     rsp, 0C0h
0x1004499b3  movsd   xmm3, qword ptr [rcx+10h]; double
0x1004499b8  mov     r11, rcx
0x1004499bb  movaps  xmmword ptr [rax-18h], xmm6
0x1004499bf  mov     rbx, rdx
0x1004499c2  movaps  xmmword ptr [rax-28h], xmm7
0x1004499c6  mov     r10d, 80000000h
0x1004499cc  movsd   xmm7, qword ptr [rcx+18h]
0x1004499d1  movaps  xmmword ptr [rax-38h], xmm9
0x1004499d6  movsd   xmm9, qword ptr [rcx+8]
0x1004499dc  movaps  xmmword ptr [rax-48h], xmm10
0x1004499e1  movaps  xmmword ptr [rax-58h], xmm12
0x1004499e6  movsd   xmm12, qword ptr [rcx]
0x1004499eb  lea     rcx, [rbp+57h+var_90]; this
0x1004499ef  unpcklpd xmm12, xmm12
0x1004499f4  unpcklpd xmm9, xmm9
0x1004499f9  movaps  xmm1, xmm12; double
0x1004499fd  movaps  xmm2, xmm9; double
0x100449a01  movsd   [rsp+0C0h+var_A0], xmm7; double
0x100449a07  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100449a0c  movsd   xmm10, [rbp+57h+var_90]
0x100449a12  xorps   xmm6, xmm6
0x100449a15  comisd  xmm6, [rbp+57h+var_88]
0x100449a1a  ja      short loc_100449A32
0x100449a1c  xor     eax, eax
0x100449a1e  comisd  xmm10, xmm6
0x100449a23  setnbe  al
0x100449a26  test    eax, eax
0x100449a28  jnz     short loc_100449A32
0x100449a2a  mov     eax, r10d
0x100449a2d  jmp     loc_100449BD1
0x100449a32  movsd   xmm3, qword ptr [r11+10h]; double
0x100449a38  lea     rcx, [rbp+57h+var_60]; this
0x100449a3c  movsd   xmm2, qword ptr [r11+28h]; double
0x100449a42  movsd   xmm1, qword ptr [r11+20h]; double
0x100449a48  movsd   [rsp+0C0h+var_A0], xmm7; double
0x100449a4e  mov     [rsp+0C0h+arg_0], rdi
0x100449a56  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100449a5b  mov     edi, 0FFFFFFFFh
0x100449a60  lea     r9d, [rdi+2]
0x100449a64  test    r8b, r8b
0x100449a67  jnz     loc_100449B0E
0x100449a6d  movsd   xmm0, qword ptr [rbx+8]
0x100449a72  lea     rdx, [rbp+57h+var_90]; struct RobustIntersections::CIntegralInterval *
0x100449a76  subsd   xmm0, qword ptr [r11+38h]
0x100449a7c  lea     rcx, [rbp+57h+var_70]; this
0x100449a80  movups  [rbp+57h+var_80], xmm9
0x100449a85  unpcklpd xmm0, xmm0
0x100449a89  movups  [rbp+57h+var_70], xmm0
0x100449a8d  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100449a92  lea     rdx, [rbp+57h+var_60]; struct RobustIntersections::CIntegralInterval *
0x100449a96  lea     rcx, [rbp+57h+var_80]; this
0x100449a9a  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100449a9f  movsd   xmm1, qword ptr [rbp+57h+var_80+8]
0x100449aa4  mov     ecx, r10d
0x100449aa7  movsd   xmm3, qword ptr [rbp+57h+var_70]
0x100449aac  comisd  xmm1, xmm3
0x100449ab0  jb      short loc_100449ADE
0x100449ab2  movsd   xmm2, qword ptr [rbp+57h+var_70+8]
0x100449ab7  movsd   xmm0, qword ptr [rbp+57h+var_80]
0x100449abc  comisd  xmm2, xmm0
0x100449ac0  jb      short loc_100449ADE
0x100449ac2  ucomisd xmm0, xmm3
0x100449ac6  jp      short loc_100449AE8
0x100449ac8  jnz     short loc_100449AE8
0x100449aca  ucomisd xmm1, xmm2
0x100449ace  jp      short loc_100449AE8
0x100449ad0  jnz     short loc_100449AE8
0x100449ad2  ucomisd xmm1, xmm0
0x100449ad6  jp      short loc_100449AE8
0x100449ad8  jnz     short loc_100449AE8
0x100449ada  xor     ecx, ecx
0x100449adc  jmp     short loc_100449AE8
0x100449ade  comisd  xmm3, xmm1
0x100449ae2  mov     ecx, r9d
0x100449ae5  cmova   ecx, edi
0x100449ae8  lea     eax, [rcx+1]
0x100449aeb  test    eax, 0FFFFFFFDh
0x100449af0  jnz     short loc_100449B03
0x100449af2  comisd  xmm6, [rbp+57h+var_88]
0x100449af7  jbe     short loc_100449B03
0x100449af9  cmp     ecx, edi
0x100449afb  mov     eax, edi
0x100449afd  cmovz   eax, r9d
0x100449b01  mov     ecx, eax
0x100449b03  test    ecx, ecx
0x100449b05  jz      short loc_100449B17
0x100449b07  mov     eax, ecx
0x100449b09  jmp     loc_100449BC9
0x100449b0e  cmp     r8b, r9b
0x100449b11  jnz     loc_100449BC6
0x100449b17  movsd   xmm0, qword ptr [rbx]
0x100449b1b  lea     rdx, [rbp+57h+var_90]; struct RobustIntersections::CIntegralInterval *
0x100449b1f  subsd   xmm0, qword ptr [r11+30h]
0x100449b25  lea     rcx, [rbp+57h+var_70]; this
0x100449b29  movups  [rbp+57h+var_80], xmm12
0x100449b2e  unpcklpd xmm0, xmm0
0x100449b32  movups  [rbp+57h+var_70], xmm0
0x100449b36  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100449b3b  lea     rdx, [rbp+57h+var_60]; struct RobustIntersections::CIntegralInterval *
0x100449b3f  lea     rcx, [rbp+57h+var_80]; this
0x100449b43  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100449b48  comisd  xmm6, [rbp+57h+var_88]
0x100449b4d  ja      short loc_100449B9B
0x100449b4f  xor     eax, eax
0x100449b51  comisd  xmm10, xmm6
0x100449b56  setnbe  al
0x100449b59  cmp     eax, r9d
0x100449b5c  jnz     short loc_100449B9B
0x100449b5e  movsd   xmm0, qword ptr [rbp+57h+var_80+8]
0x100449b63  movsd   xmm2, qword ptr [rbp+57h+var_70]
0x100449b68  comisd  xmm0, xmm2
0x100449b6c  jb      short loc_100449BBB
0x100449b6e  movsd   xmm3, qword ptr [rbp+57h+var_70+8]
0x100449b73  movsd   xmm1, qword ptr [rbp+57h+var_80]
0x100449b78  comisd  xmm3, xmm1
0x100449b7c  jb      short loc_100449BBB
0x100449b7e  ucomisd xmm1, xmm2
0x100449b82  jp      short loc_100449BC6
0x100449b84  jnz     short loc_100449BC6
0x100449b86  ucomisd xmm0, xmm3
0x100449b8a  jp      short loc_100449BC6
0x100449b8c  jnz     short loc_100449BC6
0x100449b8e  ucomisd xmm0, xmm1
0x100449b92  jp      short loc_100449BC6
0x100449b94  jnz     short loc_100449BC6
0x100449b96  xor     r10d, r10d
0x100449b99  jmp     short loc_100449BC6
0x100449b9b  movsd   xmm0, qword ptr [rbp+57h+var_70+8]
0x100449ba0  movsd   xmm2, qword ptr [rbp+57h+var_80]
0x100449ba5  comisd  xmm0, xmm2
0x100449ba9  jb      short loc_100449BBB
0x100449bab  movsd   xmm3, qword ptr [rbp+57h+var_80+8]
0x100449bb0  movsd   xmm1, qword ptr [rbp+57h+var_70]
0x100449bb5  comisd  xmm3, xmm1
0x100449bb9  jnb     short loc_100449B7E
0x100449bbb  comisd  xmm2, xmm0
0x100449bbf  mov     r10d, r9d
0x100449bc2  cmova   r10d, edi
0x100449bc6  mov     eax, r10d
0x100449bc9  mov     rdi, [rsp+0C0h+arg_0]
0x100449bd1  lea     r11, [rsp+0C0h+var_s0]
0x100449bd9  mov     rbx, [r11+18h]
0x100449bdd  movaps  xmm6, xmmword ptr [r11-10h]
0x100449be2  movaps  xmm7, xmmword ptr [r11-20h]
0x100449be7  movaps  xmm9, xmmword ptr [r11-30h]
0x100449bec  movaps  xmm10, xmmword ptr [r11-40h]
0x100449bf1  movaps  xmm12, xmmword ptr [r11-50h]
0x100449bf6  mov     rsp, r11
0x100449bf9  pop     rbp
0x100449bfa  retn
```
