# RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPair(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x10044a510`
- end: `0x10044a8ed`
- name: `?LambdaCDSortTransverseIntersectionPair@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x100449f50`

## callees

- `0x10042a400`
- `0x10042a4e0`
- `0x10042a7a0`
- `0x10044a510`
- `0x10044aed0`
- `0x10044b9f0`
- `0x10044bc40`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPair(
        __int64 a1,
        __int64 a2)
{
  int v2; // eax
  int v4; // ecx
  unsigned int v6; // r8d
  double v7; // xmm4_8
  double v8; // xmm5_8
  double v9; // xmm6_8
  double v10; // xmm3_8
  double v11; // xmm1_8
  double v12; // xmm0_8
  unsigned int *v13; // rbx
  unsigned int *v14; // rax
  int v15; // ecx
  double *v17; // r11
  int v18; // r10d
  double v19; // xmm9_8
  double v20; // xmm7_8
  double v21; // xmm8_8
  struct RobustIntersections::CIntegralInterval *v22; // rax
  int v23; // r8d
  double *v24; // r9
  double v25; // xmm2_8
  double *v26; // rcx
  double v27; // xmm0_8
  int v28; // eax
  double v29; // xmm3_8
  double v30; // xmm1_8
  int v31; // ecx
  double v33; // [rsp+30h] [rbp-138h] BYREF
  double v34; // [rsp+38h] [rbp-130h]
  double v35; // [rsp+40h] [rbp-128h] BYREF
  double v36; // [rsp+48h] [rbp-120h]
  _BYTE v37[16]; // [rsp+50h] [rbp-118h] BYREF
  _BYTE v38[16]; // [rsp+60h] [rbp-108h] BYREF
  _BYTE v39[40]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v40[40]; // [rsp+98h] [rbp-D0h] BYREF
  _BYTE v41[40]; // [rsp+C0h] [rbp-A8h] BYREF
  _BYTE v42[40]; // [rsp+E8h] [rbp-80h] BYREF

  v2 = *(_DWORD *)(a2 + 96);
  v4 = *(_DWORD *)(a1 + 96);
  if ( !v4 )
    return (unsigned int)-(v2 != 0);
  if ( v4 == 2 )
    return v2 != 2;
  if ( !v2 )
    return 1;
  if ( v2 == 2 )
    return (unsigned int)-1;
  if ( *(_BYTE *)(a1 + 112) && *(_BYTE *)(a1 + 114) && *(_BYTE *)(a2 + 112) && *(_BYTE *)(a2 + 114) )
  {
    *(_QWORD *)&v7 = *(_QWORD *)(a2 + 80) & _xmm;
    *(_QWORD *)&v8 = *(_QWORD *)(a2 + 64) & _xmm;
    *(_QWORD *)&v9 = *(_QWORD *)(a1 + 80) & _xmm;
    *(_QWORD *)&v10 = *(_QWORD *)(a1 + 64) & _xmm;
    v11 = v8 * v9;
    v12 = v7 * v10;
    if ( (v9 >= 67108864.0 || v10 >= 67108864.0 || v7 >= 67108864.0 || v8 >= 67108864.0) && v11 == v12 )
    {
      RobustIntersections::CZ<128>::CZ<128>(v42);
      RobustIntersections::CZ<128>::CZ<128>(v39);
      RobustIntersections::CZ<128>::CZ<128>(v40);
      RobustIntersections::CZ<128>::CZ<128>(v41);
      v13 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(v40, v39);
      v14 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(v42, v41);
      v6 = 0;
      v15 = v14[1];
      if ( v15 <= (int)v13[1] )
      {
        if ( v15 < (int)v13[1] )
          return (unsigned int)-1;
        if ( v15 <= 0 )
        {
          if ( v15 >= 0 )
            return v6;
          return (unsigned int)RobustIntersections::EaCompare(*((_QWORD *)v13 + 1), *v13, *((_QWORD *)v14 + 1), *v14);
        }
        else
        {
          return (unsigned int)RobustIntersections::EaCompare(*((_QWORD *)v14 + 1), *v14, *((_QWORD *)v13 + 1), *v13);
        }
      }
    }
    else if ( v11 <= v12 )
    {
      return (unsigned int)(v12 <= v11) - 1;
    }
    return 1;
  }
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v38,
    *(double *)a1,
    *(double *)(a1 + 8),
    *(double *)(a1 + 32),
    *(double *)(a1 + 40));
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v33,
    *v17,
    v17[1],
    v17[2],
    v17[3]);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v37,
    *(double *)a2,
    *(double *)(a2 + 8),
    *(double *)(a2 + 32),
    *(double *)(a2 + 40));
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v35,
    *(double *)a2,
    *(double *)(a2 + 8),
    *(double *)(a2 + 16),
    *(double *)(a2 + 24));
  v19 = v33;
  if ( v34 < 0.0 || v33 > 0.0 )
  {
    v20 = v36;
    v21 = v35;
    if ( v36 < 0.0 || v35 > 0.0 )
    {
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)v37,
        (const struct RobustIntersections::CIntegralInterval *)&v33);
      v22 = RobustIntersections::CIntegralInterval::Multiply(
              (RobustIntersections::CIntegralInterval *)v38,
              (const struct RobustIntersections::CIntegralInterval *)&v35);
      v25 = *v24;
      v26 = (double *)v22;
      v27 = *((double *)v22 + 1);
      v28 = -1;
      if ( v27 < *v24 || (v29 = v24[1], v30 = *v26, v29 < *v26) )
      {
        v18 = 1;
        if ( v25 > v27 )
          v18 = -1;
      }
      else if ( v30 == v25 && v27 == v29 && v27 == v30 )
      {
        v18 = v23;
      }
      if ( v34 >= 0.0 )
      {
        v31 = v23;
        LOBYTE(v31) = v19 > 0.0;
      }
      else
      {
        v31 = -1;
      }
      if ( v20 >= 0.0 )
      {
        v28 = v23;
        LOBYTE(v28) = v21 > 0.0;
      }
      if ( v31 * v28 == -1 )
        v18 = -v18;
    }
  }
  v6 = v18;
  if ( v18 == 0x80000000 )
    return (unsigned int)RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPairUsingExactArithmetic();
  return v6;
}

```

## disassembly

```asm
0x10044a510  push    rbx
0x10044a512  sub     rsp, 160h
0x10044a519  mov     rax, cs:__security_cookie
0x10044a520  xor     rax, rsp
0x10044a523  mov     [rsp+168h+var_58], rax
0x10044a52b  mov     eax, [rdx+60h]
0x10044a52e  mov     r11, rcx
0x10044a531  mov     ecx, [rcx+60h]
0x10044a534  mov     rbx, rdx
0x10044a537  test    ecx, ecx
0x10044a539  jnz     short loc_10044A545
0x10044a53b  neg     eax
0x10044a53d  sbb     r8d, r8d
0x10044a540  jmp     loc_10044A8D1
0x10044a545  cmp     ecx, 2
0x10044a548  jnz     short loc_10044A558
0x10044a54a  xor     r8d, r8d
0x10044a54d  cmp     eax, ecx
0x10044a54f  setnz   r8b
0x10044a553  jmp     loc_10044A8D1
0x10044a558  test    eax, eax
0x10044a55a  jnz     short loc_10044A565
0x10044a55c  lea     r8d, [rax+1]
0x10044a560  jmp     loc_10044A8D1
0x10044a565  cmp     eax, 2
0x10044a568  jnz     short loc_10044A573
0x10044a56a  lea     r8d, [rax-3]
0x10044a56e  jmp     loc_10044A8D1
0x10044a573  cmp     byte ptr [r11+70h], 0
0x10044a578  movaps  [rsp+168h+var_18], xmm6
0x10044a580  jz      loc_10044A6EC
0x10044a586  cmp     byte ptr [r11+72h], 0
0x10044a58b  jz      loc_10044A6EC
0x10044a591  cmp     byte ptr [rdx+70h], 0
0x10044a595  jz      loc_10044A6EC
0x10044a59b  cmp     byte ptr [rdx+72h], 0
0x10044a59f  jz      loc_10044A6EC
0x10044a5a5  movsd   xmm0, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10044a5ad  movsd   xmm4, qword ptr [rdx+50h]
0x10044a5b2  movsd   xmm5, qword ptr [rdx+40h]
0x10044a5b7  andps   xmm4, xmm0
0x10044a5ba  movsd   xmm6, qword ptr [r11+50h]
0x10044a5c0  andps   xmm5, xmm0
0x10044a5c3  movsd   xmm3, qword ptr [r11+40h]
0x10044a5c9  andps   xmm6, xmm0
0x10044a5cc  movsd   xmm2, cs:__real@4190000000000000
0x10044a5d4  andps   xmm3, xmm0
0x10044a5d7  comisd  xmm2, xmm6
0x10044a5db  movaps  xmm1, xmm5
0x10044a5de  movaps  xmm0, xmm4
0x10044a5e1  mulsd   xmm1, xmm6
0x10044a5e5  mulsd   xmm0, xmm3
0x10044a5e9  jbe     short loc_10044A601
0x10044a5eb  comisd  xmm2, xmm3
0x10044a5ef  jbe     short loc_10044A601
0x10044a5f1  comisd  xmm2, xmm4
0x10044a5f5  jbe     short loc_10044A601
0x10044a5f7  comisd  xmm2, xmm5
0x10044a5fb  ja      loc_10044A6C8
0x10044a601  ucomisd xmm1, xmm0
0x10044a605  jp      loc_10044A6C8
0x10044a60b  jnz     loc_10044A6C8
0x10044a611  movaps  xmm1, xmm6
0x10044a614  lea     rcx, [rsp+168h+var_80]
0x10044a61c  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a621  movaps  xmm1, xmm3
0x10044a624  lea     rcx, [rsp+168h+var_F8]
0x10044a629  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a62e  movaps  xmm1, xmm4
0x10044a631  lea     rcx, [rsp+168h+var_D0]
0x10044a639  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a63e  movaps  xmm1, xmm5
0x10044a641  lea     rcx, [rsp+168h+var_A8]
0x10044a649  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a64e  lea     rdx, [rsp+168h+var_F8]
0x10044a653  lea     rcx, [rsp+168h+var_D0]
0x10044a65b  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044a660  lea     rdx, [rsp+168h+var_A8]
0x10044a668  mov     rbx, rax
0x10044a66b  lea     rcx, [rsp+168h+var_80]
0x10044a673  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044a678  xor     r8d, r8d
0x10044a67b  mov     ecx, [rax+4]
0x10044a67e  cmp     ecx, [rbx+4]
0x10044a681  jg      short loc_10044A6CE
0x10044a683  jge     short loc_10044A690
0x10044a685  mov     r8d, 0FFFFFFFFh
0x10044a68b  jmp     loc_10044A8C9
0x10044a690  test    ecx, ecx
0x10044a692  jle     short loc_10044A6AB
0x10044a694  mov     r9d, [rbx]
0x10044a697  mov     r8, [rbx+8]
0x10044a69b  mov     edx, [rax]
0x10044a69d  mov     rcx, [rax+8]
0x10044a6a1  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044a6a6  jmp     loc_10044A8C6
0x10044a6ab  jns     loc_10044A8C9
0x10044a6b1  mov     r9d, [rax]
0x10044a6b4  mov     r8, [rax+8]
0x10044a6b8  mov     edx, [rbx]
0x10044a6ba  mov     rcx, [rbx+8]
0x10044a6be  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044a6c3  jmp     loc_10044A8C6
0x10044a6c8  comisd  xmm1, xmm0
0x10044a6cc  jbe     short loc_10044A6D9
0x10044a6ce  mov     r8d, 1
0x10044a6d4  jmp     loc_10044A8C9
0x10044a6d9  xor     r8d, r8d
0x10044a6dc  comisd  xmm0, xmm1
0x10044a6e0  setbe   r8b
0x10044a6e4  dec     r8d
0x10044a6e7  jmp     loc_10044A8C9
0x10044a6ec  movsd   xmm0, qword ptr [r11+28h]
0x10044a6f2  lea     rcx, [rsp+168h+var_108]; this
0x10044a6f7  movsd   xmm3, qword ptr [r11+20h]; double
0x10044a6fd  mov     r10d, 80000000h
0x10044a703  movsd   xmm2, qword ptr [r11+8]; double
0x10044a709  movsd   xmm1, qword ptr [r11]; double
0x10044a70e  movaps  [rsp+168h+var_28], xmm7
0x10044a716  movsd   [rsp+168h+var_148], xmm0; double
0x10044a71c  movaps  [rsp+168h+var_48], xmm9
0x10044a725  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a72a  movsd   xmm0, qword ptr [r11+18h]
0x10044a730  lea     rcx, [rsp+168h+var_138]; this
0x10044a735  movsd   xmm3, qword ptr [r11+10h]; double
0x10044a73b  movsd   xmm2, qword ptr [r11+8]; double
0x10044a741  movsd   xmm1, qword ptr [r11]; double
0x10044a746  movsd   [rsp+168h+var_148], xmm0; double
0x10044a74c  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a751  movsd   xmm0, qword ptr [rbx+28h]
0x10044a756  lea     rcx, [rsp+168h+var_118]; this
0x10044a75b  movsd   xmm3, qword ptr [rbx+20h]; double
0x10044a760  movsd   xmm2, qword ptr [rbx+8]; double
0x10044a765  movsd   xmm1, qword ptr [rbx]; double
0x10044a769  movsd   [rsp+168h+var_148], xmm0; double
0x10044a76f  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a774  movsd   xmm0, qword ptr [rbx+18h]
0x10044a779  lea     rcx, [rsp+168h+var_128]; this
0x10044a77e  movsd   xmm3, qword ptr [rbx+10h]; double
0x10044a783  movsd   xmm2, qword ptr [rbx+8]; double
0x10044a788  movsd   xmm1, qword ptr [rbx]; double
0x10044a78c  movsd   [rsp+168h+var_148], xmm0; double
0x10044a792  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a797  movsd   xmm9, [rsp+168h+var_138]
0x10044a79e  xorps   xmm6, xmm6
0x10044a7a1  xor     r8d, r8d
0x10044a7a4  comisd  xmm6, [rsp+168h+var_130]
0x10044a7aa  ja      short loc_10044A7BF
0x10044a7ac  comisd  xmm9, xmm6
0x10044a7b1  mov     eax, r8d
0x10044a7b4  setnbe  al
0x10044a7b7  test    eax, eax
0x10044a7b9  jz      loc_10044A89E
0x10044a7bf  movsd   xmm7, [rsp+168h+var_120]
0x10044a7c5  comisd  xmm6, xmm7
0x10044a7c9  movaps  [rsp+168h+var_38], xmm8
0x10044a7d2  movsd   xmm8, [rsp+168h+var_128]
0x10044a7d9  ja      short loc_10044A7EE
0x10044a7db  comisd  xmm8, xmm6
0x10044a7e0  mov     eax, r8d
0x10044a7e3  setnbe  al
0x10044a7e6  test    eax, eax
0x10044a7e8  jz      loc_10044A895
0x10044a7ee  lea     rdx, [rsp+168h+var_138]; struct RobustIntersections::CIntegralInterval *
0x10044a7f3  lea     rcx, [rsp+168h+var_118]; this
0x10044a7f8  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x10044a7fd  lea     rdx, [rsp+168h+var_128]; struct RobustIntersections::CIntegralInterval *
0x10044a802  mov     r9, rax
0x10044a805  lea     rcx, [rsp+168h+var_108]; this
0x10044a80a  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x10044a80f  movsd   xmm2, qword ptr [r9]
0x10044a814  mov     rcx, rax
0x10044a817  movsd   xmm0, qword ptr [rax+8]
0x10044a81c  mov     eax, 0FFFFFFFFh
0x10044a821  comisd  xmm0, xmm2
0x10044a825  jb      short loc_10044A854
0x10044a827  movsd   xmm3, qword ptr [r9+8]
0x10044a82d  movsd   xmm1, qword ptr [rcx]
0x10044a831  comisd  xmm3, xmm1
0x10044a835  jb      short loc_10044A854
0x10044a837  ucomisd xmm1, xmm2
0x10044a83b  jp      short loc_10044A862
0x10044a83d  jnz     short loc_10044A862
0x10044a83f  ucomisd xmm0, xmm3
0x10044a843  jp      short loc_10044A862
0x10044a845  jnz     short loc_10044A862
0x10044a847  ucomisd xmm0, xmm1
0x10044a84b  jp      short loc_10044A862
0x10044a84d  jnz     short loc_10044A862
0x10044a84f  mov     r10d, r8d
0x10044a852  jmp     short loc_10044A862
0x10044a854  comisd  xmm2, xmm0
0x10044a858  mov     r10d, 1
0x10044a85e  cmova   r10d, eax
0x10044a862  comisd  xmm6, [rsp+168h+var_130]
0x10044a868  jbe     short loc_10044A86E
0x10044a86a  mov     ecx, eax
0x10044a86c  jmp     short loc_10044A879
0x10044a86e  comisd  xmm9, xmm6
0x10044a873  mov     ecx, r8d
0x10044a876  setnbe  cl
0x10044a879  comisd  xmm6, xmm7
0x10044a87d  ja      short loc_10044A88A
0x10044a87f  comisd  xmm8, xmm6
0x10044a884  mov     eax, r8d
0x10044a887  setnbe  al
0x10044a88a  imul    eax, ecx
0x10044a88d  cmp     eax, 0FFFFFFFFh
0x10044a890  jnz     short loc_10044A895
0x10044a892  neg     r10d
0x10044a895  movaps  xmm8, [rsp+168h+var_38]
0x10044a89e  movaps  xmm9, [rsp+168h+var_48]
0x10044a8a7  mov     r8d, r10d
0x10044a8aa  movaps  xmm7, [rsp+168h+var_28]
0x10044a8b2  cmp     r10d, 80000000h
0x10044a8b9  jnz     short loc_10044A8C9
0x10044a8bb  mov     rdx, rbx
0x10044a8be  mov     rcx, r11
0x10044a8c1  call    ?LambdaCDSortTransverseIntersectionPairUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPairUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x10044a8c6  mov     r8d, eax
0x10044a8c9  movaps  xmm6, [rsp+168h+var_18]
0x10044a8d1  mov     eax, r8d
0x10044a8d4  mov     rcx, [rsp+168h+var_58]
0x10044a8dc  xor     rcx, rsp; StackCookie
0x10044a8df  call    __security_check_cookie
0x10044a8e4  add     rsp, 160h
0x10044a8eb  pop     rbx
0x10044a8ec  retn
```
