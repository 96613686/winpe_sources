# RobustIntersections::CLineSegmentIntersection::SortTransverseIntersectionsAlongCommonLineSegment(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection::PAIRING)

- ea: `0x100449f50`
- end: `0x10044a11f`
- name: `?SortTransverseIntersectionsAlongCommonLineSegment@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0W4PAIRING@12@@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10043f140`

## callees

- `0x100449f50`
- `0x10044a130`
- `0x10044a510`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::SortTransverseIntersectionsAlongCommonLineSegment(
        __int64 a1,
        __m128 *a2,
        int a3)
{
  int v3; // r8d
  int v4; // r8d
  double v6; // xmm2_8
  double v7; // xmm3_8
  __m128 v8; // xmm0
  __m128 v9; // xmm1
  __int8 v10; // al
  double v11; // xmm2_8
  __int8 v12; // al
  double v13; // xmm3_8
  __int32 v14; // eax
  __int32 v15; // eax
  double v16; // xmm2_8
  double v17; // xmm3_8
  __m128 v18; // xmm0
  __m128 v19; // xmm1
  __int8 v20; // al
  double v21; // xmm2_8
  __int8 v22; // al
  double v23; // xmm3_8
  __int32 v24; // eax
  __int32 v25; // eax
  __m128 v26; // [rsp+20h] [rbp-29h] BYREF
  __m128 v27; // [rsp+30h] [rbp-19h]
  __int64 v28; // [rsp+40h] [rbp-9h]
  __int64 v29; // [rsp+48h] [rbp-1h]
  double v30; // [rsp+50h] [rbp+7h]
  double v31; // [rsp+58h] [rbp+Fh]
  __int64 v32; // [rsp+60h] [rbp+17h]
  __int64 v33; // [rsp+68h] [rbp+1Fh]
  __int64 v34; // [rsp+70h] [rbp+27h]
  __int32 v35; // [rsp+78h] [rbp+2Fh]
  __int32 v36; // [rsp+7Ch] [rbp+33h]
  __int32 v37; // [rsp+80h] [rbp+37h]
  int v38; // [rsp+84h] [rbp+3Bh]
  int v39; // [rsp+88h] [rbp+3Fh]
  int v40; // [rsp+8Ch] [rbp+43h]
  __int8 v41; // [rsp+90h] [rbp+47h]
  __int8 v42; // [rsp+91h] [rbp+48h]
  __int8 v43; // [rsp+92h] [rbp+49h]

  if ( !a3 )
    return RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPair(a1, (__int64)a2);
  v3 = a3 - 1;
  if ( !v3 )
  {
    v16 = *(double *)&a2[2].m128_u64[1];
    v17 = *(double *)a2[2].m128_u64;
    v18 = a2[1];
    v19 = *a2;
    v38 = -a2[6].m128_i32[1];
    v39 = -a2[6].m128_i32[3];
    v40 = -a2[6].m128_i32[2];
    v20 = a2[7].m128_i8[0];
    v26 = _mm_xor_ps(v18, (__m128)_xmm);
    v41 = v20;
    *(double *)v18.m128_u64 = v16;
    v21 = v16 + *(double *)&a2[3].m128_u64[1];
    v42 = a2[7].m128_i8[2];
    v22 = a2[7].m128_i8[1];
    v29 = v18.m128_u64[0] ^ _xmm;
    v18.m128_u64[0] = a2[4].m128_u64[0];
    v27 = _mm_xor_ps(v19, (__m128)_xmm);
    v43 = v22;
    *(double *)v19.m128_u64 = v17;
    v23 = v17 + *(double *)a2[3].m128_u64;
    v35 = a2[5].m128_i32[2];
    v24 = a2[6].m128_i32[0];
    v28 = v19.m128_u64[0] ^ _xmm;
    v19.m128_u64[0] = a2[5].m128_u64[0];
    v32 = v18.m128_u64[0] ^ _xmm;
    v18.m128_u64[0] = a2[4].m128_u64[1];
    v36 = v24;
    v25 = a2[5].m128_i32[3];
    a2 = &v26;
    v37 = v25;
    v30 = v23;
    v31 = v21;
    v33 = v19.m128_u64[0] ^ _xmm;
    v34 = v18.m128_u64[0] ^ _xmm;
    return RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPair(a1, (__int64)a2);
  }
  v4 = v3 - 1;
  if ( v4 )
  {
    if ( v4 != 1 )
      return 0x80000000LL;
  }
  else
  {
    v6 = *(double *)&a2[2].m128_u64[1];
    v7 = *(double *)a2[2].m128_u64;
    v8 = a2[1];
    v9 = *a2;
    v38 = -a2[6].m128_i32[1];
    v39 = -a2[6].m128_i32[3];
    v40 = -a2[6].m128_i32[2];
    v10 = a2[7].m128_i8[0];
    v26 = _mm_xor_ps(v8, (__m128)_xmm);
    v41 = v10;
    *(double *)v8.m128_u64 = v6;
    v11 = v6 + *(double *)&a2[3].m128_u64[1];
    v42 = a2[7].m128_i8[2];
    v12 = a2[7].m128_i8[1];
    v29 = v8.m128_u64[0] ^ _xmm;
    v8.m128_u64[0] = a2[4].m128_u64[0];
    v27 = _mm_xor_ps(v9, (__m128)_xmm);
    v43 = v12;
    *(double *)v9.m128_u64 = v7;
    v13 = v7 + *(double *)a2[3].m128_u64;
    v35 = a2[5].m128_i32[2];
    v14 = a2[6].m128_i32[0];
    v28 = v9.m128_u64[0] ^ _xmm;
    v9.m128_u64[0] = a2[5].m128_u64[0];
    v32 = v8.m128_u64[0] ^ _xmm;
    v8.m128_u64[0] = a2[4].m128_u64[1];
    v36 = v14;
    v15 = a2[5].m128_i32[3];
    a2 = &v26;
    v37 = v15;
    v30 = v13;
    v31 = v11;
    v33 = v9.m128_u64[0] ^ _xmm;
    v34 = v8.m128_u64[0] ^ _xmm;
  }
  return RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPair(a1, (__int64)a2);
}

```

## disassembly

```asm
0x100449f50  push    rbp
0x100449f52  lea     rbp, [rsp-57h]
0x100449f57  sub     rsp, 0A0h
0x100449f5e  test    r8d, r8d
0x100449f61  jz      loc_10044A111
0x100449f67  sub     r8d, 1
0x100449f6b  jz      loc_10044A057
0x100449f71  sub     r8d, 1
0x100449f75  jz      short loc_100449F8F
0x100449f77  cmp     r8d, 1
0x100449f7b  jz      loc_10044A049
0x100449f81  mov     eax, 80000000h
0x100449f86  add     rsp, 0A0h
0x100449f8d  pop     rbp
0x100449f8e  retn
0x100449f8f  movaps  xmm4, cs:__xmm@80000000000000008000000000000000
0x100449f96  movsd   xmm2, qword ptr [rdx+28h]
0x100449f9b  movsd   xmm3, qword ptr [rdx+20h]
0x100449fa0  mov     eax, [rdx+64h]
0x100449fa3  movups  xmm0, xmmword ptr [rdx+10h]
0x100449fa7  neg     eax
0x100449fa9  movups  xmm1, xmmword ptr [rdx]
0x100449fac  mov     [rbp+57h+var_1C], eax
0x100449faf  mov     eax, [rdx+6Ch]
0x100449fb2  xorps   xmm0, xmm4
0x100449fb5  neg     eax
0x100449fb7  xorps   xmm1, xmm4
0x100449fba  mov     [rbp+57h+var_18], eax
0x100449fbd  mov     eax, [rdx+68h]
0x100449fc0  neg     eax
0x100449fc2  mov     [rbp+57h+var_14], eax
0x100449fc5  movzx   eax, byte ptr [rdx+70h]
0x100449fc9  movups  [rbp+57h+var_80], xmm0
0x100449fcd  mov     [rbp+57h+var_10], al
0x100449fd0  movzx   eax, byte ptr [rdx+72h]
0x100449fd4  movaps  xmm0, xmm2
0x100449fd7  addsd   xmm2, qword ptr [rdx+38h]
0x100449fdc  xorps   xmm0, xmm4
0x100449fdf  mov     [rbp+57h+var_F], al
0x100449fe2  movzx   eax, byte ptr [rdx+71h]
0x100449fe6  movsd   [rbp+57h+var_58], xmm0
0x100449feb  movsd   xmm0, qword ptr [rdx+40h]
0x100449ff0  movups  [rbp+57h+var_70], xmm1
0x100449ff4  mov     [rbp+57h+var_E], al
0x100449ff7  mov     eax, [rdx+58h]
0x100449ffa  movaps  xmm1, xmm3
0x100449ffd  addsd   xmm3, qword ptr [rdx+30h]
0x10044a002  xorps   xmm1, xmm4
0x10044a005  mov     [rbp+57h+var_28], eax
0x10044a008  mov     eax, [rdx+60h]
0x10044a00b  xorps   xmm0, xmm4
0x10044a00e  movsd   [rbp+57h+var_60], xmm1
0x10044a013  movsd   xmm1, qword ptr [rdx+50h]
0x10044a018  movsd   [rbp+57h+var_40], xmm0
0x10044a01d  xorps   xmm1, xmm4
0x10044a020  movsd   xmm0, qword ptr [rdx+48h]
0x10044a025  mov     [rbp+57h+var_24], eax
0x10044a028  xorps   xmm0, xmm4
0x10044a02b  mov     eax, [rdx+5Ch]
0x10044a02e  lea     rdx, [rbp+57h+var_80]
0x10044a032  mov     [rbp+57h+var_20], eax
0x10044a035  movsd   [rbp+57h+var_50], xmm3
0x10044a03a  movsd   [rbp+57h+var_48], xmm2
0x10044a03f  movsd   [rbp+57h+var_38], xmm1
0x10044a044  movsd   [rbp+57h+var_30], xmm0
0x10044a049  call    ?LambdaCDSortTransverseIntersectionPair@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPair(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x10044a04e  add     rsp, 0A0h
0x10044a055  pop     rbp
0x10044a056  retn
0x10044a057  movaps  xmm4, cs:__xmm@80000000000000008000000000000000
0x10044a05e  movsd   xmm2, qword ptr [rdx+28h]
0x10044a063  movsd   xmm3, qword ptr [rdx+20h]
0x10044a068  mov     eax, [rdx+64h]
0x10044a06b  movups  xmm0, xmmword ptr [rdx+10h]
0x10044a06f  neg     eax
0x10044a071  movups  xmm1, xmmword ptr [rdx]
0x10044a074  mov     [rbp+57h+var_1C], eax
0x10044a077  mov     eax, [rdx+6Ch]
0x10044a07a  xorps   xmm0, xmm4
0x10044a07d  neg     eax
0x10044a07f  xorps   xmm1, xmm4
0x10044a082  mov     [rbp+57h+var_18], eax
0x10044a085  mov     eax, [rdx+68h]
0x10044a088  neg     eax
0x10044a08a  mov     [rbp+57h+var_14], eax
0x10044a08d  movzx   eax, byte ptr [rdx+70h]
0x10044a091  movups  [rbp+57h+var_80], xmm0
0x10044a095  mov     [rbp+57h+var_10], al
0x10044a098  movzx   eax, byte ptr [rdx+72h]
0x10044a09c  movaps  xmm0, xmm2
0x10044a09f  addsd   xmm2, qword ptr [rdx+38h]
0x10044a0a4  xorps   xmm0, xmm4
0x10044a0a7  mov     [rbp+57h+var_F], al
0x10044a0aa  movzx   eax, byte ptr [rdx+71h]
0x10044a0ae  movsd   [rbp+57h+var_58], xmm0
0x10044a0b3  movsd   xmm0, qword ptr [rdx+40h]
0x10044a0b8  movups  [rbp+57h+var_70], xmm1
0x10044a0bc  mov     [rbp+57h+var_E], al
0x10044a0bf  mov     eax, [rdx+58h]
0x10044a0c2  movaps  xmm1, xmm3
0x10044a0c5  addsd   xmm3, qword ptr [rdx+30h]
0x10044a0ca  xorps   xmm1, xmm4
0x10044a0cd  mov     [rbp+57h+var_28], eax
0x10044a0d0  mov     eax, [rdx+60h]
0x10044a0d3  xorps   xmm0, xmm4
0x10044a0d6  movsd   [rbp+57h+var_60], xmm1
0x10044a0db  movsd   xmm1, qword ptr [rdx+50h]
0x10044a0e0  movsd   [rbp+57h+var_40], xmm0
0x10044a0e5  xorps   xmm1, xmm4
0x10044a0e8  movsd   xmm0, qword ptr [rdx+48h]
0x10044a0ed  mov     [rbp+57h+var_24], eax
0x10044a0f0  xorps   xmm0, xmm4
0x10044a0f3  mov     eax, [rdx+5Ch]
0x10044a0f6  lea     rdx, [rbp+57h+var_80]
0x10044a0fa  mov     [rbp+57h+var_20], eax
0x10044a0fd  movsd   [rbp+57h+var_50], xmm3
0x10044a102  movsd   [rbp+57h+var_48], xmm2
0x10044a107  movsd   [rbp+57h+var_38], xmm1
0x10044a10c  movsd   [rbp+57h+var_30], xmm0
0x10044a111  call    ?LambdaABSortTransverseIntersectionPair@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPair(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x10044a116  add     rsp, 0A0h
0x10044a11d  pop     rbp
0x10044a11e  retn
```
