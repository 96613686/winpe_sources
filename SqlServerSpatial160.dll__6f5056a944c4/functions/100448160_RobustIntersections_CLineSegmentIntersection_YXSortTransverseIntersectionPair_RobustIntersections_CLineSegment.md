# RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPair(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x100448160`
- end: `0x100448300`
- name: `?YXSortTransverseIntersectionPair@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `416`
- prototype: `static enum RobustIntersections::COMPARISON __high(const struct RobustIntersections::CLineSegmentIntersection *, const struct RobustIntersections::CLineSegmentIntersection *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10043ef20`

## callees

- `0x100448160`
- `0x100448500`
- `0x100448c60`
- `0x100449070`
- `0x100449740`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPair(
        __int64 a1,
        __int64 a2)
{
  double v3; // xmm0_8
  double v5; // xmm1_8
  double v6; // xmm2_8
  double v7; // xmm6_8
  double v8; // xmm3_8
  double v9; // xmm6_8
  double v10; // xmm1_8
  double v11; // xmm4_8
  double v12; // xmm0_8
  double v13; // xmm3_8
  double v14; // xmm2_8
  double v15; // xmm5_8
  __int64 result; // rax
  double v17; // [rsp+50h] [rbp+8h] BYREF
  double v18; // [rsp+58h] [rbp+10h] BYREF
  double v19; // [rsp+60h] [rbp+18h] BYREF
  double v20; // [rsp+68h] [rbp+20h] BYREF

  v3 = *(double *)(a1 + 56) + *(double *)(a1 + 40);
  v5 = *(double *)(a1 + 56) + *(double *)(a1 + 8);
  v6 = v3 - *(double *)(a1 + 24);
  if ( *(double *)(a1 + 56) <= v5 )
  {
    v7 = *(double *)(a1 + 56) + *(double *)(a1 + 8);
    v5 = *(double *)(a1 + 56);
  }
  else
  {
    v7 = *(double *)(a1 + 56);
  }
  if ( v3 <= v6 )
  {
    v8 = v3 - *(double *)(a1 + 24);
    v6 = *(double *)(a1 + 56) + *(double *)(a1 + 40);
  }
  else
  {
    v8 = *(double *)(a1 + 56) + *(double *)(a1 + 40);
  }
  v9 = fmin(v7, v8);
  v10 = fmax(v5, v6);
  v11 = *(double *)(a2 + 56) + *(double *)(a2 + 40);
  v12 = *(double *)(a2 + 56) + *(double *)(a2 + 8);
  v13 = v11 - *(double *)(a2 + 24);
  if ( *(double *)(a2 + 56) <= v12 )
  {
    v14 = *(double *)(a2 + 56) + *(double *)(a2 + 8);
    v12 = *(double *)(a2 + 56);
  }
  else
  {
    v14 = *(double *)(a2 + 56);
  }
  if ( v11 <= v13 )
  {
    v15 = v11 - *(double *)(a2 + 24);
    v13 = *(double *)(a2 + 56) + *(double *)(a2 + 40);
  }
  else
  {
    v15 = *(double *)(a2 + 56) + *(double *)(a2 + 40);
  }
  if ( fmax(v12, v13) > v9 )
    return 0xFFFFFFFFLL;
  if ( v10 > fmin(v14, v15) )
    return 1;
  if ( *(_DWORD *)(a1 + 88) != 2
    || *(_DWORD *)(a1 + 92) != 1
    || *(_DWORD *)(a1 + 96) != 1
    || *(_DWORD *)(a2 + 88) != 2
    || *(_DWORD *)(a2 + 92) != 1
    || *(_DWORD *)(a2 + 96) != 1 )
  {
    return RobustIntersections::CLineSegmentIntersection::YXSortSpecificPosition();
  }
  if ( *(_BYTE *)(a1 + 113) && *(_BYTE *)(a1 + 112) && *(_BYTE *)(a2 + 113) && *(_BYTE *)(a2 + 112) )
  {
    RobustIntersections::CLineSegmentIntersection::ComputeIntersectionPointYCoordinateInterval(
      (RobustIntersections::CLineSegmentIntersection *)a1,
      &v17,
      &v20);
    RobustIntersections::CLineSegmentIntersection::ComputeIntersectionPointYCoordinateInterval(
      (RobustIntersections::CLineSegmentIntersection *)a2,
      &v19,
      &v18);
    if ( v17 > v18 )
      return 1;
    if ( v19 > v20 )
      return 0xFFFFFFFFLL;
  }
  result = RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingIntervalArithmetic((double *)a1);
  if ( (_DWORD)result == 0x80000000 )
    return RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingExactArithmetic((double *)a1);
  return result;
}

```

## disassembly

```asm
0x100448160  push    rbx
0x100448162  push    rdi
0x100448163  sub     rsp, 38h
0x100448167  movsd   xmm3, qword ptr [rcx+38h]
0x10044816c  mov     rdi, rdx
0x10044816f  movaps  xmm0, xmm3
0x100448172  movaps  [rsp+48h+var_28], xmm6
0x100448177  addsd   xmm0, qword ptr [rcx+28h]
0x10044817c  movaps  xmm1, xmm3
0x10044817f  mov     rbx, rcx
0x100448182  addsd   xmm1, qword ptr [rcx+8]
0x100448187  movaps  xmm2, xmm0
0x10044818a  subsd   xmm2, qword ptr [rcx+18h]
0x10044818f  comisd  xmm3, xmm1
0x100448193  jbe     short loc_10044819A
0x100448195  movaps  xmm6, xmm3
0x100448198  jmp     short loc_1004481A0
0x10044819a  movaps  xmm6, xmm1
0x10044819d  movaps  xmm1, xmm3
0x1004481a0  comisd  xmm0, xmm2
0x1004481a4  jbe     short loc_1004481AB
0x1004481a6  movaps  xmm3, xmm0
0x1004481a9  jmp     short loc_1004481B1
0x1004481ab  movaps  xmm3, xmm2
0x1004481ae  movaps  xmm2, xmm0
0x1004481b1  movsd   xmm5, qword ptr [rdx+38h]
0x1004481b6  minsd   xmm6, xmm3
0x1004481ba  movaps  xmm4, xmm5
0x1004481bd  maxsd   xmm1, xmm2
0x1004481c1  addsd   xmm4, qword ptr [rdx+28h]
0x1004481c6  movaps  xmm0, xmm5
0x1004481c9  addsd   xmm0, qword ptr [rdx+8]
0x1004481ce  movaps  xmm3, xmm4
0x1004481d1  subsd   xmm3, qword ptr [rdx+18h]
0x1004481d6  comisd  xmm5, xmm0
0x1004481da  jbe     short loc_1004481E1
0x1004481dc  movaps  xmm2, xmm5
0x1004481df  jmp     short loc_1004481E7
0x1004481e1  movaps  xmm2, xmm0
0x1004481e4  movaps  xmm0, xmm5
0x1004481e7  comisd  xmm4, xmm3
0x1004481eb  jbe     short loc_1004481F2
0x1004481ed  movaps  xmm5, xmm4
0x1004481f0  jmp     short loc_1004481F8
0x1004481f2  movaps  xmm5, xmm3
0x1004481f5  movaps  xmm3, xmm4
0x1004481f8  maxsd   xmm0, xmm3
0x1004481fc  comisd  xmm0, xmm6
0x100448200  jbe     short loc_100448213
0x100448202  mov     eax, 0FFFFFFFFh
0x100448207  movaps  xmm6, [rsp+48h+var_28]
0x10044820c  add     rsp, 38h
0x100448210  pop     rdi
0x100448211  pop     rbx
0x100448212  retn
0x100448213  minsd   xmm2, xmm5
0x100448217  comisd  xmm1, xmm2
0x10044821b  jbe     short loc_10044822E
0x10044821d  mov     eax, 1
0x100448222  movaps  xmm6, [rsp+48h+var_28]
0x100448227  add     rsp, 38h
0x10044822b  pop     rdi
0x10044822c  pop     rbx
0x10044822d  retn
0x10044822e  cmp     dword ptr [rcx+58h], 2
0x100448232  jnz     loc_1004482EF
0x100448238  cmp     dword ptr [rcx+5Ch], 1
0x10044823c  jnz     loc_1004482EF
0x100448242  cmp     dword ptr [rcx+60h], 1
0x100448246  jnz     loc_1004482EF
0x10044824c  cmp     dword ptr [rdx+58h], 2
0x100448250  jnz     loc_1004482EF
0x100448256  cmp     dword ptr [rdx+5Ch], 1
0x10044825a  jnz     loc_1004482EF
0x100448260  cmp     dword ptr [rdx+60h], 1
0x100448264  jnz     loc_1004482EF
0x10044826a  cmp     byte ptr [rcx+71h], 0
0x10044826e  jz      short loc_1004482C7
0x100448270  cmp     byte ptr [rcx+70h], 0
0x100448274  jz      short loc_1004482C7
0x100448276  cmp     byte ptr [rdx+71h], 0
0x10044827a  jz      short loc_1004482C7
0x10044827c  cmp     byte ptr [rdx+70h], 0
0x100448280  jz      short loc_1004482C7
0x100448282  lea     r8, [rsp+48h+arg_18]; double *
0x100448287  lea     rdx, [rsp+48h+arg_0]; double *
0x10044828c  call    ?ComputeIntersectionPointYCoordinateInterval@CLineSegmentIntersection@RobustIntersections@@AEBAXAEAN0@Z; RobustIntersections::CLineSegmentIntersection::ComputeIntersectionPointYCoordinateInterval(double &,double &)
0x100448291  lea     r8, [rsp+48h+arg_8]; double *
0x100448296  mov     rcx, rdi; this
0x100448299  lea     rdx, [rsp+48h+arg_10]; double *
0x10044829e  call    ?ComputeIntersectionPointYCoordinateInterval@CLineSegmentIntersection@RobustIntersections@@AEBAXAEAN0@Z; RobustIntersections::CLineSegmentIntersection::ComputeIntersectionPointYCoordinateInterval(double &,double &)
0x1004482a3  movsd   xmm3, [rsp+48h+arg_0]
0x1004482a9  comisd  xmm3, [rsp+48h+arg_8]
0x1004482af  ja      loc_10044821D
0x1004482b5  movsd   xmm0, [rsp+48h+arg_10]
0x1004482bb  comisd  xmm0, [rsp+48h+arg_18]
0x1004482c1  ja      loc_100448202
0x1004482c7  mov     rdx, rdi
0x1004482ca  mov     rcx, rbx
0x1004482cd  call    ?YXSortTransverseIntersectionPairUsingIntervalArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingIntervalArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x1004482d2  cmp     eax, 80000000h
0x1004482d7  jnz     short loc_1004482F4
0x1004482d9  mov     rdx, rdi
0x1004482dc  mov     rcx, rbx
0x1004482df  movaps  xmm6, [rsp+48h+var_28]
0x1004482e4  add     rsp, 38h
0x1004482e8  pop     rdi
0x1004482e9  pop     rbx
0x1004482ea  jmp     ?YXSortTransverseIntersectionPairUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x1004482ef  call    ?YXSortSpecificPosition@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::YXSortSpecificPosition(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x1004482f4  movaps  xmm6, [rsp+48h+var_28]
0x1004482f9  add     rsp, 38h
0x1004482fd  pop     rdi
0x1004482fe  pop     rbx
0x1004482ff  retn
```
