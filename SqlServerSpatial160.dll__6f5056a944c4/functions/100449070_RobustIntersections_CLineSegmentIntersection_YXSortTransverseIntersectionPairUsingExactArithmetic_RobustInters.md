# RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x100449070`
- end: `0x100449733`
- name: `?YXSortTransverseIntersectionPairUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `1731`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x100448160`

## callees

- `0x10042a4e0`
- `0x10042a7a0`
- `0x100449070`
- `0x10044b3c0`
- `0x10044b4a0`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::YXSortTransverseIntersectionPairUsingExactArithmetic(
        double *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  unsigned int v6; // edi
  unsigned int v7; // ecx
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  double v12; // xmm1_8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  double v15; // xmm1_8
  unsigned __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v22; // r9
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  double v26; // xmm1_8
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rcx
  double v29; // xmm1_8
  unsigned __int64 v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rax
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36; // [rsp+24h] [rbp-DCh]
  __int128 *v37; // [rsp+28h] [rbp-D8h]
  __int128 v38; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v39; // [rsp+40h] [rbp-C0h]
  int v40; // [rsp+50h] [rbp-B0h]
  unsigned int v41; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+5Ch] [rbp-A4h]
  __int64 v43; // [rsp+60h] [rbp-A0h]
  unsigned int v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+94h] [rbp-6Ch]
  __int64 v46; // [rsp+98h] [rbp-68h]
  unsigned int v47; // [rsp+C8h] [rbp-38h] BYREF
  int v48; // [rsp+CCh] [rbp-34h]
  __int64 v49; // [rsp+D0h] [rbp-30h]
  unsigned int v50; // [rsp+100h] [rbp+0h] BYREF
  int v51; // [rsp+104h] [rbp+4h]
  __int64 v52; // [rsp+108h] [rbp+8h]
  _BYTE v53[4]; // [rsp+138h] [rbp+38h] BYREF
  int v54; // [rsp+13Ch] [rbp+3Ch]
  _BYTE v55[4]; // [rsp+170h] [rbp+70h] BYREF
  int v56; // [rsp+174h] [rbp+74h]
  _BYTE v57[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v58; // [rsp+1ACh] [rbp+ACh]
  _BYTE v59[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v60; // [rsp+1E4h] [rbp+E4h]
  _BYTE v61[4]; // [rsp+218h] [rbp+118h] BYREF
  int v62; // [rsp+21Ch] [rbp+11Ch]
  _BYTE v63[56]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v64[56]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v65[56]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v66[56]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v67[56]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v68[56]; // [rsp+368h] [rbp+268h] BYREF
  _BYTE v69[56]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v70[56]; // [rsp+3D8h] [rbp+2D8h] BYREF
  _BYTE v71[56]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v72[56]; // [rsp+448h] [rbp+348h] BYREF

  RobustIntersections::CZ<256>::CZ<256>(v53);
  RobustIntersections::CZ<256>::CZ<256>(v55);
  RobustIntersections::CZ<256>::CZ<256>(v71);
  RobustIntersections::CZ<256>::CZ<256>(v68);
  RobustIntersections::CZ<256>::CZ<256>(v67);
  RobustIntersections::CZ<256>::CZ<256>(v63);
  RobustIntersections::CZ<256>::CZ<256>(v57);
  RobustIntersections::CZ<256>::CZ<256>(v65);
  RobustIntersections::CZ<256>::CZ<256>(v59);
  RobustIntersections::CZ<256>::CZ<256>(v72);
  RobustIntersections::CZ<256>::CZ<256>(v70);
  RobustIntersections::CZ<256>::CZ<256>(v69);
  RobustIntersections::CZ<256>::CZ<256>(v64);
  RobustIntersections::CZ<256>::CZ<256>(v61);
  RobustIntersections::CZ<256>::CZ<256>(&v47);
  RobustIntersections::CZ<256>::CZ<256>(&v50);
  RobustIntersections::CZ<128>::Multiply(v53, v67);
  RobustIntersections::CZ<128>::Multiply(v55, v68);
  v56 = -v56;
  RobustIntersections::CZ<128>::Add(v53, v55);
  v56 = -v56;
  RobustIntersections::CZ<128>::Multiply(v63, v67);
  RobustIntersections::CZ<128>::Multiply(v57, v68);
  v58 = -v58;
  RobustIntersections::CZ<128>::Add(v63, v57);
  v58 = -v58;
  RobustIntersections::CZ<128>::Multiply(v65, v69);
  RobustIntersections::CZ<128>::Multiply(v59, v70);
  v60 = -v60;
  RobustIntersections::CZ<128>::Add(v65, v59);
  v60 = -v60;
  RobustIntersections::CZ<128>::Multiply(v64, v69);
  RobustIntersections::CZ<128>::Multiply(v61, v70);
  v62 = -v62;
  RobustIntersections::CZ<128>::Add(v64, v61);
  v62 = -v62;
  RobustIntersections::CZ<128>::Multiply(v63, v65);
  RobustIntersections::CZ<128>::Multiply(v64, v53);
  RobustIntersections::CZ<128>::Multiply(v53, v65);
  v2 = RobustIntersections::CZ<128>::Multiply(v71, v63);
  v3 = RobustIntersections::CZ<128>::Multiply(&v47, v53);
  RobustIntersections::CZ<128>::Add(v3, v2);
  v4 = RobustIntersections::CZ<128>::Multiply(v72, v64);
  v5 = RobustIntersections::CZ<128>::Multiply(&v50, v53);
  RobustIntersections::CZ<128>::Add(v5, v4);
  v6 = 0;
  v7 = 0;
  if ( v54 == -1 )
  {
    if ( v51 <= v48 )
    {
      if ( v51 >= v48 )
      {
        if ( v51 <= 0 )
        {
          if ( v51 >= 0 )
            goto LABEL_9;
          v8 = v50;
          v9 = v52;
          v10 = v47;
          v11 = v49;
        }
        else
        {
          v8 = v47;
          v9 = v49;
          v10 = v50;
          v11 = v52;
        }
        v7 = RobustIntersections::EaCompare(v11, v10, v9, v8);
LABEL_9:
        if ( !v7 )
        {
          v12 = *a1;
          v13 = 0;
          v35 = 9;
          v40 = 0;
          v38 = 0;
          v39 = 0;
          if ( v12 <= 0.0 )
          {
            if ( v12 >= 0.0 )
            {
              v36 = 0;
            }
            else
            {
              *(_QWORD *)&v15 = *(_QWORD *)&v12 ^ _xmm;
              v16 = 0;
              if ( v15 >= 9.223372036854776e18 )
              {
                v15 = v15 - 9.223372036854776e18;
                if ( v15 < 9.223372036854776e18 )
                  v16 = 0x8000000000000000uLL;
              }
              v36 = -1;
              v13 = v16 + (unsigned int)(int)v15;
            }
          }
          else
          {
            v14 = 0;
            if ( v12 >= 9.223372036854776e18 )
            {
              v12 = v12 - 9.223372036854776e18;
              if ( v12 < 9.223372036854776e18 )
                v14 = 0x8000000000000000uLL;
            }
            v36 = 1;
            v13 = v14 + (unsigned int)(int)v12;
          }
          *(_QWORD *)&v38 = v13;
          v37 = &v38;
          RobustIntersections::CZ<256>::CZ<256>(&v44);
          RobustIntersections::CZ<256>::CZ<256>(v66);
          RobustIntersections::CZ<256>::CZ<256>(&v41);
          v17 = RobustIntersections::CZ<128>::Multiply(&v35, v63);
          v18 = RobustIntersections::CZ<128>::Multiply(&v44, v53);
          RobustIntersections::CZ<128>::Add(v18, v17);
          v19 = RobustIntersections::CZ<128>::Multiply(v66, v64);
          v20 = RobustIntersections::CZ<128>::Multiply(&v41, v53);
          RobustIntersections::CZ<128>::Add(v20, v19);
          if ( v42 <= v45 )
          {
            if ( v42 >= v45 )
            {
              if ( v42 <= 0 )
              {
                if ( v42 < 0 )
                  return RobustIntersections::EaCompare(v46, v44, v43, v41);
                return v6;
              }
              return (unsigned int)RobustIntersections::EaCompare(v43, v41, v46, v44);
            }
            return 0xFFFFFFFFLL;
          }
          return 1;
        }
        return v7;
      }
      return 0xFFFFFFFFLL;
    }
    return 1;
  }
  if ( v48 > v51 )
    return 1;
  if ( v48 < v51 )
    return 0xFFFFFFFFLL;
  if ( v48 <= 0 )
  {
    if ( v48 >= 0 )
      goto LABEL_35;
    v22 = v47;
    v23 = v49;
    v24 = v50;
    v25 = v52;
  }
  else
  {
    v22 = v50;
    v23 = v52;
    v24 = v47;
    v25 = v49;
  }
  v7 = RobustIntersections::EaCompare(v25, v24, v23, v22);
LABEL_35:
  if ( !v7 )
  {
    v26 = *a1;
    v27 = 0;
    v35 = 9;
    v40 = 0;
    v38 = 0;
    v39 = 0;
    if ( v26 <= 0.0 )
    {
      if ( v26 >= 0.0 )
      {
        v36 = 0;
      }
      else
      {
        *(_QWORD *)&v29 = *(_QWORD *)&v26 ^ _xmm;
        v30 = 0;
        if ( v29 >= 9.223372036854776e18 )
        {
          v29 = v29 - 9.223372036854776e18;
          if ( v29 < 9.223372036854776e18 )
            v30 = 0x8000000000000000uLL;
        }
        v36 = -1;
        v27 = v30 + (unsigned int)(int)v29;
      }
    }
    else
    {
      v28 = 0;
      if ( v26 >= 9.223372036854776e18 )
      {
        v26 = v26 - 9.223372036854776e18;
        if ( v26 < 9.223372036854776e18 )
          v28 = 0x8000000000000000uLL;
      }
      v36 = 1;
      v27 = v28 + (unsigned int)(int)v26;
    }
    *(_QWORD *)&v38 = v27;
    v37 = &v38;
    RobustIntersections::CZ<256>::CZ<256>(&v44);
    RobustIntersections::CZ<256>::CZ<256>(v66);
    RobustIntersections::CZ<256>::CZ<256>(&v41);
    v31 = RobustIntersections::CZ<128>::Multiply(&v35, v63);
    v32 = RobustIntersections::CZ<128>::Multiply(&v44, v53);
    RobustIntersections::CZ<128>::Add(v32, v31);
    v33 = RobustIntersections::CZ<128>::Multiply(v66, v64);
    v34 = RobustIntersections::CZ<128>::Multiply(&v41, v53);
    RobustIntersections::CZ<128>::Add(v34, v33);
    if ( v45 <= v42 )
    {
      if ( v45 >= v42 )
      {
        if ( v45 > 0 )
          return RobustIntersections::EaCompare(v46, v44, v43, v41);
        if ( v45 >= 0 )
          return v6;
        return (unsigned int)RobustIntersections::EaCompare(v43, v41, v46, v44);
      }
      return 0xFFFFFFFFLL;
    }
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x100449070  mov     [rsp-8+arg_0], rbx
0x100449075  mov     [rsp-8+arg_8], rsi
0x10044907a  mov     [rsp-8+arg_10], rdi
0x10044907f  mov     [rsp-8+arg_18], r14
0x100449084  push    rbp
0x100449085  lea     rbp, [rsp-390h]
0x10044908d  sub     rsp, 490h
0x100449094  mov     rax, cs:__security_cookie
0x10044909b  xor     rax, rsp
0x10044909e  mov     [rbp+390h+var_10], rax
0x1004490a5  movsd   xmm1, qword ptr [rcx]
0x1004490a9  mov     rsi, rcx
0x1004490ac  lea     rcx, [rbp+390h+var_358]
0x1004490b0  mov     r14, rdx
0x1004490b3  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004490b8  movsd   xmm1, qword ptr [rsi+8]
0x1004490bd  lea     rcx, [rbp+390h+var_320]
0x1004490c1  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004490c6  movsd   xmm1, qword ptr [rsi+8]
0x1004490cb  lea     rcx, [rbp+390h+var_80]
0x1004490d2  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004490d7  movsd   xmm1, qword ptr [rsi+10h]
0x1004490dc  lea     rcx, [rbp+390h+var_128]
0x1004490e3  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004490e8  movsd   xmm1, qword ptr [rsi+18h]
0x1004490ed  lea     rcx, [rbp+390h+var_160]
0x1004490f4  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004490f9  movsd   xmm1, qword ptr [rsi+20h]
0x1004490fe  lea     rcx, [rbp+390h+var_240]
0x100449105  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044910a  movsd   xmm1, qword ptr [rsi+28h]
0x10044910f  lea     rcx, [rbp+390h+var_2E8]
0x100449116  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044911b  movsd   xmm1, qword ptr [r14]
0x100449120  lea     rcx, [rbp+390h+var_1D0]
0x100449127  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044912c  movsd   xmm1, qword ptr [r14+8]
0x100449132  lea     rcx, [rbp+390h+var_2B0]
0x100449139  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044913e  movsd   xmm1, qword ptr [r14+8]
0x100449144  lea     rcx, [rbp+390h+var_48]
0x10044914b  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100449150  movsd   xmm1, qword ptr [r14+10h]
0x100449156  lea     rcx, [rbp+390h+var_B8]
0x10044915d  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100449162  movsd   xmm1, qword ptr [r14+18h]
0x100449168  lea     rcx, [rbp+390h+var_F0]
0x10044916f  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100449174  movsd   xmm1, qword ptr [r14+20h]
0x10044917a  lea     rcx, [rbp+390h+var_208]
0x100449181  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100449186  movsd   xmm1, qword ptr [r14+28h]
0x10044918c  lea     rcx, [rbp+390h+var_278]
0x100449193  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100449198  movsd   xmm1, qword ptr [rsi+38h]
0x10044919d  lea     rcx, [rbp+390h+var_3C8]
0x1004491a1  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004491a6  movsd   xmm1, qword ptr [r14+38h]
0x1004491ac  lea     rcx, [rbp+390h+var_390]
0x1004491b0  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x1004491b5  lea     rdx, [rbp+390h+var_160]
0x1004491bc  lea     rcx, [rbp+390h+var_358]
0x1004491c0  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004491c5  lea     rdx, [rbp+390h+var_128]
0x1004491cc  lea     rcx, [rbp+390h+var_320]
0x1004491d0  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004491d5  neg     [rbp+390h+var_31C]
0x1004491d8  lea     rdx, [rbp+390h+var_320]
0x1004491dc  lea     rcx, [rbp+390h+var_358]
0x1004491e0  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x1004491e5  neg     [rbp+390h+var_31C]
0x1004491e8  lea     rdx, [rbp+390h+var_160]
0x1004491ef  lea     rcx, [rbp+390h+var_240]
0x1004491f6  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004491fb  lea     rdx, [rbp+390h+var_128]
0x100449202  lea     rcx, [rbp+390h+var_2E8]
0x100449209  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044920e  neg     [rbp+390h+var_2E4]
0x100449214  lea     rdx, [rbp+390h+var_2E8]
0x10044921b  lea     rcx, [rbp+390h+var_240]
0x100449222  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100449227  neg     [rbp+390h+var_2E4]
0x10044922d  lea     rdx, [rbp+390h+var_F0]
0x100449234  lea     rcx, [rbp+390h+var_1D0]
0x10044923b  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449240  lea     rdx, [rbp+390h+var_B8]
0x100449247  lea     rcx, [rbp+390h+var_2B0]
0x10044924e  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449253  neg     [rbp+390h+var_2AC]
0x100449259  lea     rdx, [rbp+390h+var_2B0]
0x100449260  lea     rcx, [rbp+390h+var_1D0]
0x100449267  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044926c  neg     [rbp+390h+var_2AC]
0x100449272  lea     rdx, [rbp+390h+var_F0]
0x100449279  lea     rcx, [rbp+390h+var_208]
0x100449280  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449285  lea     rdx, [rbp+390h+var_B8]
0x10044928c  lea     rcx, [rbp+390h+var_278]
0x100449293  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100449298  neg     [rbp+390h+var_274]
0x10044929e  lea     rdx, [rbp+390h+var_278]
0x1004492a5  lea     rcx, [rbp+390h+var_208]
0x1004492ac  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x1004492b1  neg     [rbp+390h+var_274]
0x1004492b7  lea     rdx, [rbp+390h+var_1D0]
0x1004492be  lea     rcx, [rbp+390h+var_240]
0x1004492c5  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004492ca  lea     rdx, [rbp+390h+var_358]
0x1004492ce  lea     rcx, [rbp+390h+var_208]
0x1004492d5  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004492da  lea     rdx, [rbp+390h+var_1D0]
0x1004492e1  lea     rcx, [rbp+390h+var_358]
0x1004492e5  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004492ea  lea     rdx, [rbp+390h+var_240]
0x1004492f1  lea     rcx, [rbp+390h+var_80]
0x1004492f8  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004492fd  lea     rdx, [rbp+390h+var_358]
0x100449301  mov     rbx, rax
0x100449304  lea     rcx, [rbp+390h+var_3C8]
0x100449308  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044930d  mov     rcx, rax
0x100449310  mov     rdx, rbx
0x100449313  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100449318  lea     rdx, [rbp+390h+var_208]
0x10044931f  lea     rcx, [rbp+390h+var_48]
0x100449326  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044932b  lea     rdx, [rbp+390h+var_358]
0x10044932f  mov     rbx, rax
0x100449332  lea     rcx, [rbp+390h+var_390]
0x100449336  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044933b  mov     rcx, rax
0x10044933e  mov     rdx, rbx
0x100449341  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100449346  xor     edi, edi
0x100449348  cmp     [rbp+390h+var_354], 0FFFFFFFFh
0x10044934c  mov     ecx, edi
0x10044934e  jnz     loc_100449524
0x100449354  mov     eax, [rbp+390h+var_38C]
0x100449357  cmp     eax, [rbp+390h+var_3C4]
0x10044935a  jg      loc_10044952C
0x100449360  jl      loc_100449538
0x100449366  test    eax, eax
0x100449368  jle     short loc_10044937B
0x10044936a  mov     r9d, [rbp+390h+var_3C8]
0x10044936e  mov     r8, [rbp+390h+var_3C0]
0x100449372  mov     edx, [rbp+390h+var_390]
0x100449375  mov     rcx, [rbp+390h+var_388]
0x100449379  jmp     short loc_10044938C
0x10044937b  jns     short loc_100449393
0x10044937d  mov     r9d, [rbp+390h+var_390]
0x100449381  mov     r8, [rbp+390h+var_388]
0x100449385  mov     edx, [rbp+390h+var_3C8]
0x100449388  mov     rcx, [rbp+390h+var_3C0]
0x10044938c  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x100449391  mov     ecx, eax
0x100449393  test    ecx, ecx
0x100449395  jnz     loc_100449705
0x10044939b  movsd   xmm1, qword ptr [rsi]
0x10044939f  xor     eax, eax
0x1004493a1  xorps   xmm0, xmm0
0x1004493a4  mov     [rsp+490h+var_470], 9
0x1004493ac  xorps   xmm2, xmm2
0x1004493af  mov     [rsp+490h+var_440], eax
0x1004493b3  comisd  xmm1, xmm2
0x1004493b7  movups  [rsp+490h+var_460], xmm0
0x1004493bc  movups  [rsp+490h+var_450], xmm0
0x1004493c1  jbe     short loc_1004493FC
0x1004493c3  movsd   xmm0, cs:__real@43e0000000000000
0x1004493cb  xor     ecx, ecx
0x1004493cd  comisd  xmm1, xmm0
0x1004493d1  jb      short loc_1004493EA
0x1004493d3  subsd   xmm1, xmm0
0x1004493d7  comisd  xmm1, xmm0
0x1004493db  jnb     short loc_1004493EA
0x1004493dd  mov     rax, 8000000000000000h
0x1004493e7  mov     rcx, rax
0x1004493ea  cvttsd2si rax, xmm1
0x1004493ef  mov     [rsp+490h+var_46C], 1
0x1004493f7  add     rax, rcx
0x1004493fa  jmp     short loc_100449446
0x1004493fc  comisd  xmm2, xmm1
0x100449400  jbe     short loc_100449442
0x100449402  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x100449409  xor     ecx, ecx
0x10044940b  movsd   xmm0, cs:__real@43e0000000000000
0x100449413  comisd  xmm1, xmm0
0x100449417  jb      short loc_100449430
0x100449419  subsd   xmm1, xmm0
0x10044941d  comisd  xmm1, xmm0
0x100449421  jnb     short loc_100449430
0x100449423  mov     rax, 8000000000000000h
0x10044942d  mov     rcx, rax
0x100449430  cvttsd2si rax, xmm1
0x100449435  mov     [rsp+490h+var_46C], 0FFFFFFFFh
0x10044943d  add     rax, rcx
0x100449440  jmp     short loc_100449446
0x100449442  mov     [rsp+490h+var_46C], edi
0x100449446  movsd   xmm1, qword ptr [rsi+30h]
0x10044944b  lea     rcx, [rbp+390h+var_400]
0x10044944f  mov     dword ptr [rsp+490h+var_460], eax
0x100449453  shr     rax, 20h
0x100449457  mov     dword ptr [rsp+490h+var_460+4], eax
0x10044945b  lea     rax, [rsp+490h+var_460]
0x100449460  mov     [rsp+490h+var_468], rax
0x100449465  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044946a  movsd   xmm1, qword ptr [r14]
0x10044946f  lea     rcx, [rbp+390h+var_198]
0x100449476  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044947b  movsd   xmm1, qword ptr [r14+30h]
0x100449481  lea     rcx, [rsp+490h+var_438]
0x100449486  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044948b  lea     rdx, [rbp+390h+var_240]
0x100449492  lea     rcx, [rsp+490h+var_470]
0x100449497  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044949c  lea     rdx, [rbp+390h+var_358]
0x1004494a0  mov     rbx, rax
0x1004494a3  lea     rcx, [rbp+390h+var_400]
0x1004494a7  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004494ac  mov     rcx, rax
0x1004494af  mov     rdx, rbx
0x1004494b2  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x1004494b7  lea     rdx, [rbp+390h+var_208]
0x1004494be  lea     rcx, [rbp+390h+var_198]
0x1004494c5  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004494ca  lea     rdx, [rbp+390h+var_358]
0x1004494ce  mov     rbx, rax
0x1004494d1  lea     rcx, [rsp+490h+var_438]
0x1004494d6  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x1004494db  mov     rcx, rax
0x1004494de  mov     rdx, rbx
0x1004494e1  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x1004494e6  mov     eax, [rsp+490h+var_434]
0x1004494ea  cmp     eax, [rbp+390h+var_3FC]
0x1004494ed  jg      loc_1004496CB
0x1004494f3  jl      loc_1004496D6
0x1004494f9  test    eax, eax
0x1004494fb  jg      loc_1004496E9
0x100449501  jns     loc_100449701
0x100449507  mov     r9d, [rsp+490h+var_438]
0x10044950c  mov     r8, [rsp+490h+var_430]
0x100449511  mov     edx, [rbp+390h+var_400]
0x100449514  mov     rcx, [rbp+390h+var_3F8]
0x100449518  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044951d  mov     edi, eax
0x10044951f  jmp     loc_100449707
0x100449524  mov     eax, [rbp+390h+var_3C4]
0x100449527  cmp     eax, [rbp+390h+var_38C]
0x10044952a  jle     short loc_100449536
0x10044952c  mov     eax, 1
0x100449531  jmp     loc_100449707
0x100449536  jge     short loc_100449542
0x100449538  mov     eax, 0FFFFFFFFh
0x10044953d  jmp     loc_100449707
0x100449542  test    eax, eax
0x100449544  jle     short loc_100449557
0x100449546  mov     r9d, [rbp+390h+var_390]
0x10044954a  mov     r8, [rbp+390h+var_388]
0x10044954e  mov     edx, [rbp+390h+var_3C8]
0x100449551  mov     rcx, [rbp+390h+var_3C0]
0x100449555  jmp     short loc_100449568
0x100449557  jns     short loc_10044956F
0x100449559  mov     r9d, [rbp+390h+var_3C8]
0x10044955d  mov     r8, [rbp+390h+var_3C0]
0x100449561  mov     edx, [rbp+390h+var_390]
0x100449564  mov     rcx, [rbp+390h+var_388]
0x100449568  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044956d  mov     ecx, eax
0x10044956f  test    ecx, ecx
0x100449571  jnz     loc_100449705
0x100449577  movsd   xmm1, qword ptr [rsi]
0x10044957b  xor     eax, eax
0x10044957d  xorps   xmm0, xmm0
0x100449580  mov     [rsp+490h+var_470], 9
0x100449588  xorps   xmm2, xmm2
0x10044958b  mov     [rsp+490h+var_440], eax
0x10044958f  comisd  xmm1, xmm2
0x100449593  movups  [rsp+490h+var_460], xmm0
0x100449598  movups  [rsp+490h+var_450], xmm0
0x10044959d  jbe     short loc_1004495D8
0x10044959f  movsd   xmm0, cs:__real@43e0000000000000
0x1004495a7  xor     ecx, ecx
0x1004495a9  comisd  xmm1, xmm0
0x1004495ad  jb      short loc_1004495C6
0x1004495af  subsd   xmm1, xmm0
0x1004495b3  comisd  xmm1, xmm0
0x1004495b7  jnb     short loc_1004495C6
0x1004495b9  mov     rax, 8000000000000000h
0x1004495c3  mov     rcx, rax
0x1004495c6  cvttsd2si rax, xmm1
0x1004495cb  mov     [rsp+490h+var_46C], 1
0x1004495d3  add     rax, rcx
0x1004495d6  jmp     short loc_100449622
0x1004495d8  comisd  xmm2, xmm1
0x1004495dc  jbe     short loc_10044961E
0x1004495de  xorps   xmm1, cs:__xmm@80000000000000008000000000000000
0x1004495e5  xor     ecx, ecx
0x1004495e7  movsd   xmm0, cs:__real@43e0000000000000
0x1004495ef  comisd  xmm1, xmm0
0x1004495f3  jb      short loc_10044960C
0x1004495f5  subsd   xmm1, xmm0
  ... truncated ...
```
