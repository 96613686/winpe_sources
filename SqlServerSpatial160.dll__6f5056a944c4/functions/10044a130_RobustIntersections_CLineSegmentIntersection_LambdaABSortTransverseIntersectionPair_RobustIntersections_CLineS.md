# RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPair(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x10044a130`
- end: `0x10044a504`
- name: `?LambdaABSortTransverseIntersectionPair@CLineSegmentIntersection@RobustIntersections@@SA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `980`
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
- `0x10044a130`
- `0x10044a900`
- `0x10044b9f0`
- `0x10044bc40`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPair(
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
  double v17; // xmm6_8
  double *v18; // r11
  double v19; // xmm6_8
  int v20; // r10d
  double v21; // xmm9_8
  double v22; // xmm7_8
  double v23; // xmm8_8
  struct RobustIntersections::CIntegralInterval *v24; // rax
  int v25; // r8d
  double *v26; // r9
  double v27; // xmm2_8
  double *v28; // rcx
  double v29; // xmm0_8
  int v30; // eax
  double v31; // xmm3_8
  double v32; // xmm1_8
  int v33; // ecx
  double v35; // [rsp+30h] [rbp-138h] BYREF
  double v36; // [rsp+38h] [rbp-130h]
  double v37; // [rsp+40h] [rbp-128h] BYREF
  double v38; // [rsp+48h] [rbp-120h]
  _BYTE v39[16]; // [rsp+50h] [rbp-118h] BYREF
  _BYTE v40[16]; // [rsp+60h] [rbp-108h] BYREF
  _BYTE v41[40]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v42[40]; // [rsp+98h] [rbp-D0h] BYREF
  _BYTE v43[40]; // [rsp+C0h] [rbp-A8h] BYREF
  _BYTE v44[40]; // [rsp+E8h] [rbp-80h] BYREF

  v2 = *(_DWORD *)(a2 + 92);
  v4 = *(_DWORD *)(a1 + 92);
  if ( !v4 )
    return (unsigned int)-(v2 != 0);
  if ( v4 == 2 )
    return v2 != 2;
  if ( !v2 )
    return 1;
  if ( v2 == 2 )
    return (unsigned int)-1;
  if ( *(_BYTE *)(a1 + 112) && *(_BYTE *)(a1 + 113) && *(_BYTE *)(a2 + 112) && *(_BYTE *)(a2 + 113) )
  {
    *(_QWORD *)&v7 = *(_QWORD *)(a2 + 72) & _xmm;
    *(_QWORD *)&v8 = *(_QWORD *)(a2 + 64) & _xmm;
    *(_QWORD *)&v9 = *(_QWORD *)(a1 + 72) & _xmm;
    *(_QWORD *)&v10 = *(_QWORD *)(a1 + 64) & _xmm;
    v11 = v8 * v9;
    v12 = v7 * v10;
    if ( (v9 >= 67108864.0 || v10 >= 67108864.0 || v7 >= 67108864.0 || v8 >= 67108864.0) && v11 == v12 )
    {
      RobustIntersections::CZ<128>::CZ<128>(v44);
      RobustIntersections::CZ<128>::CZ<128>(v41);
      RobustIntersections::CZ<128>::CZ<128>(v42);
      RobustIntersections::CZ<128>::CZ<128>(v43);
      v13 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(v42, v41);
      v14 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(v44, v43);
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
  v17 = *(double *)(a1 + 24);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v40,
    *(double *)(a1 + 32),
    *(double *)(a1 + 40),
    *(double *)(a1 + 16),
    v17);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v35,
    *v18,
    v18[1],
    v18[2],
    v17);
  v19 = *(double *)(a2 + 24);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v39,
    *(double *)(a2 + 32),
    *(double *)(a2 + 40),
    *(double *)(a2 + 16),
    v19);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)&v37,
    *(double *)a2,
    *(double *)(a2 + 8),
    *(double *)(a2 + 16),
    v19);
  v21 = v35;
  if ( v36 < 0.0 || v35 > 0.0 )
  {
    v22 = v38;
    v23 = v37;
    if ( v38 < 0.0 || v37 > 0.0 )
    {
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)v39,
        (const struct RobustIntersections::CIntegralInterval *)&v35);
      v24 = RobustIntersections::CIntegralInterval::Multiply(
              (RobustIntersections::CIntegralInterval *)v40,
              (const struct RobustIntersections::CIntegralInterval *)&v37);
      v27 = *v26;
      v28 = (double *)v24;
      v29 = *((double *)v24 + 1);
      v30 = -1;
      if ( v29 < *v26 || (v31 = v26[1], v32 = *v28, v31 < *v28) )
      {
        v20 = 1;
        if ( v27 > v29 )
          v20 = -1;
      }
      else if ( v32 == v27 && v29 == v31 && v29 == v32 )
      {
        v20 = v25;
      }
      if ( v36 >= 0.0 )
      {
        v33 = v25;
        LOBYTE(v33) = v21 > 0.0;
      }
      else
      {
        v33 = -1;
      }
      if ( v22 >= 0.0 )
      {
        v30 = v25;
        LOBYTE(v30) = v23 > 0.0;
      }
      if ( v33 * v30 == -1 )
        v20 = -v20;
    }
  }
  v6 = v20;
  if ( v20 == 0x80000000 )
    return (unsigned int)RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPairUsingExactArithmetic();
  return v6;
}

```

## disassembly

```asm
0x10044a130  push    rbx
0x10044a132  sub     rsp, 160h
0x10044a139  mov     rax, cs:__security_cookie
0x10044a140  xor     rax, rsp
0x10044a143  mov     [rsp+168h+var_58], rax
0x10044a14b  mov     eax, [rdx+5Ch]
0x10044a14e  mov     r11, rcx
0x10044a151  mov     ecx, [rcx+5Ch]
0x10044a154  mov     rbx, rdx
0x10044a157  test    ecx, ecx
0x10044a159  jnz     short loc_10044A165
0x10044a15b  neg     eax
0x10044a15d  sbb     r8d, r8d
0x10044a160  jmp     loc_10044A4E8
0x10044a165  cmp     ecx, 2
0x10044a168  jnz     short loc_10044A178
0x10044a16a  xor     r8d, r8d
0x10044a16d  cmp     eax, ecx
0x10044a16f  setnz   r8b
0x10044a173  jmp     loc_10044A4E8
0x10044a178  test    eax, eax
0x10044a17a  jnz     short loc_10044A185
0x10044a17c  lea     r8d, [rax+1]
0x10044a180  jmp     loc_10044A4E8
0x10044a185  cmp     eax, 2
0x10044a188  jnz     short loc_10044A193
0x10044a18a  lea     r8d, [rax-3]
0x10044a18e  jmp     loc_10044A4E8
0x10044a193  cmp     byte ptr [r11+70h], 0
0x10044a198  movaps  [rsp+168h+var_18], xmm6
0x10044a1a0  jz      loc_10044A30C
0x10044a1a6  cmp     byte ptr [r11+71h], 0
0x10044a1ab  jz      loc_10044A30C
0x10044a1b1  cmp     byte ptr [rdx+70h], 0
0x10044a1b5  jz      loc_10044A30C
0x10044a1bb  cmp     byte ptr [rdx+71h], 0
0x10044a1bf  jz      loc_10044A30C
0x10044a1c5  movsd   xmm0, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x10044a1cd  movsd   xmm4, qword ptr [rdx+48h]
0x10044a1d2  movsd   xmm5, qword ptr [rdx+40h]
0x10044a1d7  andps   xmm4, xmm0
0x10044a1da  movsd   xmm6, qword ptr [r11+48h]
0x10044a1e0  andps   xmm5, xmm0
0x10044a1e3  movsd   xmm3, qword ptr [r11+40h]
0x10044a1e9  andps   xmm6, xmm0
0x10044a1ec  movsd   xmm2, cs:__real@4190000000000000
0x10044a1f4  andps   xmm3, xmm0
0x10044a1f7  comisd  xmm2, xmm6
0x10044a1fb  movaps  xmm1, xmm5
0x10044a1fe  movaps  xmm0, xmm4
0x10044a201  mulsd   xmm1, xmm6
0x10044a205  mulsd   xmm0, xmm3
0x10044a209  jbe     short loc_10044A221
0x10044a20b  comisd  xmm2, xmm3
0x10044a20f  jbe     short loc_10044A221
0x10044a211  comisd  xmm2, xmm4
0x10044a215  jbe     short loc_10044A221
0x10044a217  comisd  xmm2, xmm5
0x10044a21b  ja      loc_10044A2E8
0x10044a221  ucomisd xmm1, xmm0
0x10044a225  jp      loc_10044A2E8
0x10044a22b  jnz     loc_10044A2E8
0x10044a231  movaps  xmm1, xmm6
0x10044a234  lea     rcx, [rsp+168h+var_80]
0x10044a23c  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a241  movaps  xmm1, xmm3
0x10044a244  lea     rcx, [rsp+168h+var_F8]
0x10044a249  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a24e  movaps  xmm1, xmm4
0x10044a251  lea     rcx, [rsp+168h+var_D0]
0x10044a259  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a25e  movaps  xmm1, xmm5
0x10044a261  lea     rcx, [rsp+168h+var_A8]
0x10044a269  call    ??0?$CZ@$0IA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<128>::CZ<128>(double)
0x10044a26e  lea     rdx, [rsp+168h+var_F8]
0x10044a273  lea     rcx, [rsp+168h+var_D0]
0x10044a27b  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044a280  lea     rdx, [rsp+168h+var_A8]
0x10044a288  mov     rbx, rax
0x10044a28b  lea     rcx, [rsp+168h+var_80]
0x10044a293  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044a298  xor     r8d, r8d
0x10044a29b  mov     ecx, [rax+4]
0x10044a29e  cmp     ecx, [rbx+4]
0x10044a2a1  jg      short loc_10044A2EE
0x10044a2a3  jge     short loc_10044A2B0
0x10044a2a5  mov     r8d, 0FFFFFFFFh
0x10044a2ab  jmp     loc_10044A4E0
0x10044a2b0  test    ecx, ecx
0x10044a2b2  jle     short loc_10044A2CB
0x10044a2b4  mov     r9d, [rbx]
0x10044a2b7  mov     r8, [rbx+8]
0x10044a2bb  mov     edx, [rax]
0x10044a2bd  mov     rcx, [rax+8]
0x10044a2c1  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044a2c6  jmp     loc_10044A4DD
0x10044a2cb  jns     loc_10044A4E0
0x10044a2d1  mov     r9d, [rax]
0x10044a2d4  mov     r8, [rax+8]
0x10044a2d8  mov     edx, [rbx]
0x10044a2da  mov     rcx, [rbx+8]
0x10044a2de  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044a2e3  jmp     loc_10044A4DD
0x10044a2e8  comisd  xmm1, xmm0
0x10044a2ec  jbe     short loc_10044A2F9
0x10044a2ee  mov     r8d, 1
0x10044a2f4  jmp     loc_10044A4E0
0x10044a2f9  xor     r8d, r8d
0x10044a2fc  comisd  xmm0, xmm1
0x10044a300  setbe   r8b
0x10044a304  dec     r8d
0x10044a307  jmp     loc_10044A4E0
0x10044a30c  movsd   xmm6, qword ptr [r11+18h]
0x10044a312  lea     rcx, [rsp+168h+var_108]; this
0x10044a317  movsd   xmm3, qword ptr [r11+10h]; double
0x10044a31d  mov     r10d, 80000000h
0x10044a323  movsd   xmm2, qword ptr [r11+28h]; double
0x10044a329  movsd   xmm1, qword ptr [r11+20h]; double
0x10044a32f  movaps  [rsp+168h+var_28], xmm7
0x10044a337  movsd   [rsp+168h+var_148], xmm6; double
0x10044a33d  movaps  [rsp+168h+var_48], xmm9
0x10044a346  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a34b  movsd   xmm3, qword ptr [r11+10h]; double
0x10044a351  lea     rcx, [rsp+168h+var_138]; this
0x10044a356  movsd   xmm2, qword ptr [r11+8]; double
0x10044a35c  movsd   xmm1, qword ptr [r11]; double
0x10044a361  movsd   [rsp+168h+var_148], xmm6; double
0x10044a367  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a36c  movsd   xmm6, qword ptr [rbx+18h]
0x10044a371  lea     rcx, [rsp+168h+var_118]; this
0x10044a376  movsd   xmm3, qword ptr [rbx+10h]; double
0x10044a37b  movsd   xmm2, qword ptr [rbx+28h]; double
0x10044a380  movsd   xmm1, qword ptr [rbx+20h]; double
0x10044a385  movsd   [rsp+168h+var_148], xmm6; double
0x10044a38b  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a390  movsd   xmm3, qword ptr [rbx+10h]; double
0x10044a395  lea     rcx, [rsp+168h+var_128]; this
0x10044a39a  movsd   xmm2, qword ptr [rbx+8]; double
0x10044a39f  movsd   xmm1, qword ptr [rbx]; double
0x10044a3a3  movsd   [rsp+168h+var_148], xmm6; double
0x10044a3a9  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x10044a3ae  movsd   xmm9, [rsp+168h+var_138]
0x10044a3b5  xorps   xmm6, xmm6
0x10044a3b8  xor     r8d, r8d
0x10044a3bb  comisd  xmm6, [rsp+168h+var_130]
0x10044a3c1  ja      short loc_10044A3D6
0x10044a3c3  comisd  xmm9, xmm6
0x10044a3c8  mov     eax, r8d
0x10044a3cb  setnbe  al
0x10044a3ce  test    eax, eax
0x10044a3d0  jz      loc_10044A4B5
0x10044a3d6  movsd   xmm7, [rsp+168h+var_120]
0x10044a3dc  comisd  xmm6, xmm7
0x10044a3e0  movaps  [rsp+168h+var_38], xmm8
0x10044a3e9  movsd   xmm8, [rsp+168h+var_128]
0x10044a3f0  ja      short loc_10044A405
0x10044a3f2  comisd  xmm8, xmm6
0x10044a3f7  mov     eax, r8d
0x10044a3fa  setnbe  al
0x10044a3fd  test    eax, eax
0x10044a3ff  jz      loc_10044A4AC
0x10044a405  lea     rdx, [rsp+168h+var_138]; struct RobustIntersections::CIntegralInterval *
0x10044a40a  lea     rcx, [rsp+168h+var_118]; this
0x10044a40f  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x10044a414  lea     rdx, [rsp+168h+var_128]; struct RobustIntersections::CIntegralInterval *
0x10044a419  mov     r9, rax
0x10044a41c  lea     rcx, [rsp+168h+var_108]; this
0x10044a421  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x10044a426  movsd   xmm2, qword ptr [r9]
0x10044a42b  mov     rcx, rax
0x10044a42e  movsd   xmm0, qword ptr [rax+8]
0x10044a433  mov     eax, 0FFFFFFFFh
0x10044a438  comisd  xmm0, xmm2
0x10044a43c  jb      short loc_10044A46B
0x10044a43e  movsd   xmm3, qword ptr [r9+8]
0x10044a444  movsd   xmm1, qword ptr [rcx]
0x10044a448  comisd  xmm3, xmm1
0x10044a44c  jb      short loc_10044A46B
0x10044a44e  ucomisd xmm1, xmm2
0x10044a452  jp      short loc_10044A479
0x10044a454  jnz     short loc_10044A479
0x10044a456  ucomisd xmm0, xmm3
0x10044a45a  jp      short loc_10044A479
0x10044a45c  jnz     short loc_10044A479
0x10044a45e  ucomisd xmm0, xmm1
0x10044a462  jp      short loc_10044A479
0x10044a464  jnz     short loc_10044A479
0x10044a466  mov     r10d, r8d
0x10044a469  jmp     short loc_10044A479
0x10044a46b  comisd  xmm2, xmm0
0x10044a46f  mov     r10d, 1
0x10044a475  cmova   r10d, eax
0x10044a479  comisd  xmm6, [rsp+168h+var_130]
0x10044a47f  jbe     short loc_10044A485
0x10044a481  mov     ecx, eax
0x10044a483  jmp     short loc_10044A490
0x10044a485  comisd  xmm9, xmm6
0x10044a48a  mov     ecx, r8d
0x10044a48d  setnbe  cl
0x10044a490  comisd  xmm6, xmm7
0x10044a494  ja      short loc_10044A4A1
0x10044a496  comisd  xmm8, xmm6
0x10044a49b  mov     eax, r8d
0x10044a49e  setnbe  al
0x10044a4a1  imul    eax, ecx
0x10044a4a4  cmp     eax, 0FFFFFFFFh
0x10044a4a7  jnz     short loc_10044A4AC
0x10044a4a9  neg     r10d
0x10044a4ac  movaps  xmm8, [rsp+168h+var_38]
0x10044a4b5  movaps  xmm9, [rsp+168h+var_48]
0x10044a4be  mov     r8d, r10d
0x10044a4c1  movaps  xmm7, [rsp+168h+var_28]
0x10044a4c9  cmp     r10d, 80000000h
0x10044a4d0  jnz     short loc_10044A4E0
0x10044a4d2  mov     rdx, rbx
0x10044a4d5  mov     rcx, r11
0x10044a4d8  call    ?LambdaABSortTransverseIntersectionPairUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z; RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPairUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)
0x10044a4dd  mov     r8d, eax
0x10044a4e0  movaps  xmm6, [rsp+168h+var_18]
0x10044a4e8  mov     eax, r8d
0x10044a4eb  mov     rcx, [rsp+168h+var_58]
0x10044a4f3  xor     rcx, rsp; StackCookie
0x10044a4f6  call    __security_check_cookie
0x10044a4fb  add     rsp, 160h
0x10044a502  pop     rbx
0x10044a503  retn
```
