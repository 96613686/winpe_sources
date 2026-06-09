# RobustIntersections::CLineSegmentIntersection::LocateTransverseIntersectionRelativeToLine(double const * const)

- ea: `0x100447890`
- end: `0x100448155`
- name: `?LocateTransverseIntersectionRelativeToLine@CLineSegmentIntersection@RobustIntersections@@QEBA?AW4SIDEINDICATOR@12@QEBN@Z`
- size: `2245`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x10043efe0`

## callees

- `0x100401210`
- `0x10042a4e0`
- `0x10042a680`
- `0x10042a7a0`
- `0x100447250`
- `0x100447890`
- `0x10044b3c0`
- `0x10044b4a0`
- `0x10044b9f0`
- `0x10044bc40`
- `0x100468a30`

## pseudocode

```c
__int64 __fastcall RobustIntersections::CLineSegmentIntersection::LocateTransverseIntersectionRelativeToLine(
        double *a1,
        double *a2)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // r15d
  unsigned int v7; // r14d
  unsigned int v8; // eax
  double v9; // xmm10_8
  double v10; // xmm8_8
  double v11; // xmm9_8
  double v12; // xmm6_8
  double v13; // xmm7_8
  int v14; // ecx
  int v15; // eax
  const struct RobustIntersections::CIntegralInterval *v16; // rdx
  RobustIntersections::CIntegralInterval *v17; // rcx
  double *v18; // rax
  double *v19; // r8
  double v20; // xmm2_8
  unsigned int v21; // ecx
  double v22; // xmm0_8
  double v23; // xmm1_8
  double v24; // xmm3_8
  bool v25; // zf
  unsigned int v26; // edx
  char *j; // rcx
  __int64 v28; // r9
  int v29; // edx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // ebx
  unsigned int v33; // edx
  char *v34; // rcx
  __int64 v35; // r9
  int v36; // edx
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // eax
  int v41; // ecx
  __int64 v42; // r9
  void *v43; // r8
  __int64 v44; // rdx
  void *v45; // rcx
  unsigned int v46; // edx
  char *i; // rcx
  __int64 v48; // r9
  int v49; // edx
  __int64 v50; // rcx
  int v51; // eax
  unsigned int v52; // ebx
  unsigned int v53; // edx
  char *v54; // rcx
  __int64 v55; // r9
  int v56; // edx
  __int64 v57; // rcx
  int v58; // eax
  unsigned int v59; // ebx
  int v60; // ecx
  unsigned int *v62; // [rsp+28h] [rbp-D8h]
  unsigned int *v63; // [rsp+28h] [rbp-D8h]
  unsigned int *v64; // [rsp+28h] [rbp-D8h]
  double v65[2]; // [rsp+30h] [rbp-D0h] BYREF
  double v66[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v67[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v68[16]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v69; // [rsp+70h] [rbp-90h] BYREF
  int v70; // [rsp+74h] [rbp-8Ch]
  void *Destination; // [rsp+78h] [rbp-88h]
  unsigned int v72; // [rsp+A8h] [rbp-58h] BYREF
  int v73; // [rsp+ACh] [rbp-54h]
  void *v74; // [rsp+B0h] [rbp-50h]
  unsigned int v75; // [rsp+E0h] [rbp-20h] BYREF
  int v76; // [rsp+E4h] [rbp-1Ch]
  int v77[12]; // [rsp+E8h] [rbp-18h]
  unsigned int v78; // [rsp+118h] [rbp+18h] BYREF
  int v79; // [rsp+11Ch] [rbp+1Ch]
  int v80[12]; // [rsp+120h] [rbp+20h]
  _BYTE v81[4]; // [rsp+150h] [rbp+50h] BYREF
  int v82; // [rsp+154h] [rbp+54h]
  _BYTE v83[4]; // [rsp+188h] [rbp+88h] BYREF
  int v84; // [rsp+18Ch] [rbp+8Ch]
  _BYTE v85[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v86; // [rsp+1C4h] [rbp+C4h]
  _BYTE v87[4]; // [rsp+1F8h] [rbp+F8h] BYREF
  int v88; // [rsp+1FCh] [rbp+FCh]
  _BYTE v89[56]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v90[56]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v91[56]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v92[56]; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int128 Source; // [rsp+310h] [rbp+210h] BYREF
  __int128 v94; // [rsp+320h] [rbp+220h]
  __int128 v95; // [rsp+330h] [rbp+230h]
  __int128 v96; // [rsp+340h] [rbp+240h]
  __int64 v97; // [rsp+350h] [rbp+250h]

  v4 = ComputeDeterminantExactSign();
  v5 = ComputeDeterminantExactSign();
  v6 = v5;
  if ( v4 == v5 )
    return v4;
  if ( !v4 )
    return v5;
  if ( !v5 )
    return v4;
  v7 = ComputeDeterminantExactSign();
  v8 = ComputeDeterminantExactSign();
  if ( v7 == v8 )
    return v7;
  if ( !v7 )
    return v8;
  if ( !v8 )
    return v7;
  v9 = a1[3];
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v66,
    *a1,
    a1[1],
    a1[2],
    v9);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v67,
    a1[4],
    a1[5],
    a1[2],
    v9);
  v10 = *a2;
  v11 = a2[1];
  v12 = a2[2] - *a2;
  v13 = a2[3] - v11;
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v65,
    *a1,
    a1[1],
    v12,
    v13);
  RobustIntersections::CIntegralInterval::CIntegralInterval(
    (RobustIntersections::CIntegralInterval *)v68,
    v10 - a1[6],
    v11 - a1[7],
    v12,
    v13);
  if ( v66[1] >= 0.0 )
    v14 = v66[0] > 0.0;
  else
    v14 = -1;
  if ( v65[1] >= 0.0 )
    v15 = v65[0] > 0.0;
  else
    v15 = -1;
  if ( v14 && v15 )
  {
    if ( v14 * v15 == 1 )
    {
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)v66,
        (const struct RobustIntersections::CIntegralInterval *)v68);
      v16 = (const struct RobustIntersections::CIntegralInterval *)v65;
      v17 = (RobustIntersections::CIntegralInterval *)v67;
    }
    else
    {
      RobustIntersections::CIntegralInterval::Multiply(
        (RobustIntersections::CIntegralInterval *)v67,
        (const struct RobustIntersections::CIntegralInterval *)v65);
      v16 = (const struct RobustIntersections::CIntegralInterval *)v68;
      v17 = (RobustIntersections::CIntegralInterval *)v66;
    }
    v18 = (double *)RobustIntersections::CIntegralInterval::Multiply(v17, v16);
    v20 = *v19;
    v21 = 0x80000000;
    v22 = v18[1];
    if ( v22 < *v19 || (v23 = *v18, v24 = v19[1], v24 < *v18) )
    {
      v21 = 1;
      if ( v20 > v22 )
        v21 = -1;
    }
    else if ( v23 == v20 && v22 == v24 && v22 == v23 )
    {
      v21 = 0;
    }
    if ( v21 != 0x80000000 )
    {
      if ( v21 == -1 )
        return v4;
      v4 = 0;
      v25 = v21 == 1;
      goto LABEL_90;
    }
  }
  RobustIntersections::CZ<256>::CZ<256>(&v69);
  RobustIntersections::CZ<256>::CZ<256>(v81);
  RobustIntersections::CZ<256>::CZ<256>(v90);
  RobustIntersections::CZ<256>::CZ<256>(v89);
  RobustIntersections::CZ<128>::Multiply(&v69, v89);
  RobustIntersections::CZ<128>::Multiply(v81, v90);
  v82 = -v82;
  RobustIntersections::CZ<128>::Add(&v69, v81);
  v82 = -v82;
  RobustIntersections::CZ<256>::CZ<256>(&v72);
  RobustIntersections::CZ<256>::CZ<256>(v83);
  RobustIntersections::CZ<128>::Multiply(&v72, v89);
  RobustIntersections::CZ<128>::Multiply(v83, v90);
  v84 = -v84;
  RobustIntersections::CZ<128>::Add(&v72, v83);
  v84 = -v84;
  RobustIntersections::CZ<256>::CZ<256>(&v75);
  RobustIntersections::CZ<256>::CZ<256>(v85);
  RobustIntersections::CZ<256>::CZ<256>(v92);
  RobustIntersections::CZ<256>::CZ<256>(v91);
  RobustIntersections::CZ<128>::Multiply(&v75, v91);
  RobustIntersections::CZ<128>::Multiply(v85, v92);
  v86 = -v86;
  RobustIntersections::CZ<128>::Add(&v75, v85);
  v86 = -v86;
  RobustIntersections::CZ<256>::CZ<256>(&v78);
  RobustIntersections::CZ<256>::CZ<256>(v87);
  RobustIntersections::CZ<128>::Multiply(&v78, v91);
  RobustIntersections::CZ<128>::Multiply(v87, v92);
  v88 = -v88;
  RobustIntersections::CZ<128>::Add(&v78, v87);
  v88 = -v88;
  if ( v76 * v70 != 1 )
  {
    v46 = v72;
    for ( i = (char *)v74 + 4 * v72; v46; --v46 )
    {
      v25 = *((_DWORD *)i - 1) == 0;
      i -= 4;
      if ( !v25 )
        break;
    }
    v48 = 1;
    if ( v46 )
      v48 = v46;
    v49 = v75;
    v50 = *(_QWORD *)v77 + 4LL * v75;
    if ( v75 )
    {
      do
      {
        v25 = *(_DWORD *)(v50 - 4) == 0;
        v50 -= 4;
        if ( !v25 )
          break;
        --v49;
      }
      while ( v49 );
    }
    v51 = 1;
    if ( v49 )
      v51 = v49;
    v97 = 0;
    LODWORD(v62) = v51;
    Source = 0;
    v52 = v51 + v48;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    RobustIntersections::EaMultiply(
      (RobustIntersections *)&Source,
      (unsigned int *)(unsigned int)(v51 + v48),
      (int)v74,
      (const unsigned int *)v48,
      v77[0],
      v62,
      SLODWORD(v65[0]));
    memcpy_s(v74, 4LL * v52, &Source, 4LL * v52);
    v53 = v69;
    v73 *= v76;
    v54 = (char *)Destination + 4 * v69;
    if ( v69 )
    {
      do
      {
        v25 = *((_DWORD *)v54 - 1) == 0;
        v54 -= 4;
        if ( !v25 )
          break;
        --v53;
      }
      while ( v53 );
    }
    v55 = 1;
    if ( v53 )
      v55 = v53;
    v56 = v78;
    v57 = *(_QWORD *)v80 + 4LL * v78;
    if ( v78 )
    {
      do
      {
        v25 = *(_DWORD *)(v57 - 4) == 0;
        v57 -= 4;
        if ( !v25 )
          break;
        --v56;
      }
      while ( v56 );
    }
    v58 = 1;
    if ( v56 )
      v58 = v56;
    v97 = 0;
    LODWORD(v64) = v58;
    Source = 0;
    v59 = v58 + v55;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    RobustIntersections::EaMultiply(
      (RobustIntersections *)&Source,
      (unsigned int *)(unsigned int)(v58 + v55),
      (int)Destination,
      (const unsigned int *)v55,
      v80[0],
      v64,
      SLODWORD(v65[0]));
    memcpy_s(Destination, 4LL * v59, &Source, 4LL * v59);
    v40 = 0;
    v60 = v70 * v79;
    v70 = v60;
    if ( v60 > v73 )
    {
      v40 = 1;
      goto LABEL_88;
    }
    if ( v60 < v73 )
    {
      v40 = -1;
      goto LABEL_88;
    }
    if ( v60 > 0 )
    {
LABEL_59:
      v42 = v72;
      v43 = v74;
      v44 = v69;
      v45 = Destination;
LABEL_87:
      v40 = RobustIntersections::EaCompare(v45, v44, v43, v42);
      goto LABEL_88;
    }
    if ( v60 >= 0 )
      goto LABEL_88;
LABEL_86:
    v42 = v69;
    v43 = Destination;
    v44 = v72;
    v45 = v74;
    goto LABEL_87;
  }
  v26 = v69;
  for ( j = (char *)Destination + 4 * v69; v26; --v26 )
  {
    v25 = *((_DWORD *)j - 1) == 0;
    j -= 4;
    if ( !v25 )
      break;
  }
  v28 = 1;
  if ( v26 )
    v28 = v26;
  v29 = v78;
  v30 = *(_QWORD *)v80 + 4LL * v78;
  if ( v78 )
  {
    do
    {
      v25 = *(_DWORD *)(v30 - 4) == 0;
      v30 -= 4;
      if ( !v25 )
        break;
      --v29;
    }
    while ( v29 );
  }
  v31 = 1;
  if ( v29 )
    v31 = v29;
  v97 = 0;
  LODWORD(v62) = v31;
  Source = 0;
  v32 = v31 + v28;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  RobustIntersections::EaMultiply(
    (RobustIntersections *)&Source,
    (unsigned int *)(unsigned int)(v31 + v28),
    (int)Destination,
    (const unsigned int *)v28,
    v80[0],
    v62,
    SLODWORD(v65[0]));
  memcpy_s(Destination, 4LL * v32, &Source, 4LL * v32);
  v33 = v72;
  v70 *= v79;
  v34 = (char *)v74 + 4 * v72;
  if ( v72 )
  {
    do
    {
      v25 = *((_DWORD *)v34 - 1) == 0;
      v34 -= 4;
      if ( !v25 )
        break;
      --v33;
    }
    while ( v33 );
  }
  v35 = 1;
  if ( v33 )
    v35 = v33;
  v36 = v75;
  v37 = *(_QWORD *)v77 + 4LL * v75;
  if ( v75 )
  {
    do
    {
      v25 = *(_DWORD *)(v37 - 4) == 0;
      v37 -= 4;
      if ( !v25 )
        break;
      --v36;
    }
    while ( v36 );
  }
  v38 = 1;
  if ( v36 )
    v38 = v36;
  v97 = 0;
  LODWORD(v63) = v38;
  Source = 0;
  v39 = v38 + v35;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  RobustIntersections::EaMultiply(
    (RobustIntersections *)&Source,
    (unsigned int *)(unsigned int)(v38 + v35),
    (int)v74,
    (const unsigned int *)v35,
    v77[0],
    v63,
    SLODWORD(v65[0]));
  memcpy_s(v74, 4LL * v39, &Source, 4LL * v39);
  v40 = 0;
  v41 = v76 * v73;
  v73 = v41;
  if ( v41 <= v70 )
  {
    if ( v41 < v70 )
    {
      v40 = -1;
      goto LABEL_88;
    }
    if ( v41 <= 0 )
    {
      if ( v41 >= 0 )
        goto LABEL_88;
      goto LABEL_59;
    }
    goto LABEL_86;
  }
  v40 = 1;
LABEL_88:
  if ( v40 == -1 )
    return v4;
  v4 = 0;
  v25 = v40 == 1;
LABEL_90:
  if ( v25 )
    return v6;
  return v4;
}

```

## disassembly

```asm
0x100447890  push    rbp
0x100447892  push    rbx
0x100447893  push    rsi
0x100447894  push    rdi
0x100447895  push    r15
0x100447897  lea     rbp, [rsp-2C0h]
0x10044789f  sub     rsp, 3C0h
0x1004478a6  mov     rax, cs:__security_cookie
0x1004478ad  xor     rax, rsp
0x1004478b0  mov     [rbp+2E0h+var_80], rax
0x1004478b7  movsd   xmm3, qword ptr [rcx+38h]
0x1004478bc  mov     rsi, rdx
0x1004478bf  movsd   xmm2, qword ptr [rcx+30h]
0x1004478c4  mov     rbx, rcx
0x1004478c7  movsd   xmm1, qword ptr [rdx+18h]
0x1004478cc  movsd   xmm0, qword ptr [rdx+10h]
0x1004478d1  subsd   xmm3, qword ptr [rdx+8]
0x1004478d6  subsd   xmm2, qword ptr [rdx]
0x1004478da  subsd   xmm1, qword ptr [rdx+8]
0x1004478df  subsd   xmm0, qword ptr [rdx]
0x1004478e3  call    ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
0x1004478e8  movsd   xmm3, qword ptr [rbx+38h]
0x1004478ed  mov     edi, eax
0x1004478ef  movsd   xmm2, qword ptr [rbx+30h]
0x1004478f4  subsd   xmm3, qword ptr [rsi+8]
0x1004478f9  subsd   xmm2, qword ptr [rsi]
0x1004478fd  movsd   xmm1, qword ptr [rsi+18h]
0x100447902  movsd   xmm0, qword ptr [rsi+10h]
0x100447907  subsd   xmm1, qword ptr [rsi+8]
0x10044790c  addsd   xmm3, qword ptr [rbx+8]
0x100447911  addsd   xmm2, qword ptr [rbx]
0x100447915  subsd   xmm0, qword ptr [rsi]
0x100447919  call    ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
0x10044791e  mov     r15d, eax
0x100447921  cmp     edi, eax
0x100447923  jz      loc_100448136
0x100447929  test    edi, edi
0x10044792b  jnz     short loc_100447934
0x10044792d  mov     edi, eax
0x10044792f  jmp     loc_100448136
0x100447934  test    r15d, r15d
0x100447937  jz      loc_100448136
0x10044793d  movsd   xmm3, qword ptr [rbx+38h]
0x100447942  movsd   xmm2, qword ptr [rbx+30h]
0x100447947  subsd   xmm3, qword ptr [rsi+8]
0x10044794c  subsd   xmm2, qword ptr [rsi]
0x100447950  movsd   xmm1, qword ptr [rsi+18h]
0x100447955  movsd   xmm0, qword ptr [rsi+10h]
0x10044795a  subsd   xmm1, qword ptr [rsi+8]
0x10044795f  addsd   xmm3, qword ptr [rbx+28h]
0x100447964  addsd   xmm2, qword ptr [rbx+20h]
0x100447969  subsd   xmm0, qword ptr [rsi]
0x10044796d  mov     [rsp+3E0h+arg_10], r14
0x100447975  call    ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
0x10044797a  movsd   xmm0, qword ptr [rbx+38h]
0x10044797f  mov     r14d, eax
0x100447982  subsd   xmm0, qword ptr [rsi+8]
0x100447987  movsd   xmm3, qword ptr [rbx+28h]
0x10044798c  subsd   xmm3, qword ptr [rbx+18h]
0x100447991  movsd   xmm2, qword ptr [rbx+20h]
0x100447996  subsd   xmm2, qword ptr [rbx+10h]
0x10044799b  movsd   xmm1, qword ptr [rsi+18h]
0x1004479a0  subsd   xmm1, qword ptr [rsi+8]
0x1004479a5  addsd   xmm3, xmm0
0x1004479a9  movsd   xmm0, qword ptr [rbx+30h]
0x1004479ae  subsd   xmm0, qword ptr [rsi]
0x1004479b2  addsd   xmm2, xmm0
0x1004479b6  movsd   xmm0, qword ptr [rsi+10h]
0x1004479bb  subsd   xmm0, qword ptr [rsi]
0x1004479bf  call    ?ComputeDeterminantExactSign@@YA?AW4SIGNINDICATOR@RobustIntersections@@NNNN@Z; ComputeDeterminantExactSign(double,double,double,double)
0x1004479c4  cmp     r14d, eax
0x1004479c7  jz      short loc_1004479D9
0x1004479c9  test    r14d, r14d
0x1004479cc  jnz     short loc_1004479D5
0x1004479ce  mov     edi, eax
0x1004479d0  jmp     loc_10044812E
0x1004479d5  test    eax, eax
0x1004479d7  jnz     short loc_1004479E1
0x1004479d9  mov     edi, r14d
0x1004479dc  jmp     loc_10044812E
0x1004479e1  movsd   xmm3, qword ptr [rbx+10h]; double
0x1004479e6  lea     rcx, [rsp+3E0h+var_3A0]; this
0x1004479eb  movsd   xmm2, qword ptr [rbx+8]; double
0x1004479f0  movsd   xmm1, qword ptr [rbx]; double
0x1004479f4  movaps  [rsp+3E0h+var_30], xmm6
0x1004479fc  movaps  [rsp+3E0h+var_40], xmm7
0x100447a04  movaps  [rsp+3E0h+var_50], xmm8
0x100447a0d  movaps  [rsp+3E0h+var_60], xmm9
0x100447a16  movaps  [rsp+3E0h+var_70], xmm10
0x100447a1f  movsd   xmm10, qword ptr [rbx+18h]
0x100447a25  movsd   qword ptr [rsp+3E0h+var_3C0], xmm10; double
0x100447a2c  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100447a31  movsd   xmm3, qword ptr [rbx+10h]; double
0x100447a36  lea     rcx, [rsp+3E0h+var_390]; this
0x100447a3b  movsd   xmm2, qword ptr [rbx+28h]; double
0x100447a40  movsd   xmm1, qword ptr [rbx+20h]; double
0x100447a45  movsd   qword ptr [rsp+3E0h+var_3C0], xmm10; double
0x100447a4c  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100447a51  movsd   xmm6, qword ptr [rsi+10h]
0x100447a56  lea     rcx, [rsp+3E0h+var_3B0]; this
0x100447a5b  movsd   xmm8, qword ptr [rsi]
0x100447a60  movsd   xmm9, qword ptr [rsi+8]
0x100447a66  subsd   xmm6, xmm8
0x100447a6b  movsd   xmm7, qword ptr [rsi+18h]
0x100447a70  movsd   xmm2, qword ptr [rbx+8]; double
0x100447a75  subsd   xmm7, xmm9
0x100447a7a  movsd   xmm1, qword ptr [rbx]; double
0x100447a7e  movaps  xmm3, xmm6; double
0x100447a81  movsd   qword ptr [rsp+3E0h+var_3C0], xmm7; double
0x100447a87  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100447a8c  subsd   xmm9, qword ptr [rbx+38h]
0x100447a92  subsd   xmm8, qword ptr [rbx+30h]
0x100447a98  movaps  xmm3, xmm6; double
0x100447a9b  movsd   qword ptr [rsp+3E0h+var_3C0], xmm7; double
0x100447aa1  lea     rcx, [rsp+3E0h+var_380]; this
0x100447aa6  movaps  xmm2, xmm9; double
0x100447aaa  movaps  xmm1, xmm8; double
0x100447aae  call    ??0CIntegralInterval@RobustIntersections@@QEAA@NNNN@Z; RobustIntersections::CIntegralInterval::CIntegralInterval(double,double,double,double)
0x100447ab3  movaps  xmm9, [rsp+3E0h+var_60]
0x100447abc  xorps   xmm1, xmm1
0x100447abf  comisd  xmm1, [rsp+3E0h+var_398]
0x100447ac5  mov     r14d, 0FFFFFFFFh
0x100447acb  movaps  xmm8, [rsp+3E0h+var_50]
0x100447ad4  movaps  xmm7, [rsp+3E0h+var_40]
0x100447adc  movaps  xmm6, [rsp+3E0h+var_30]
0x100447ae4  jbe     short loc_100447AEB
0x100447ae6  mov     ecx, r14d
0x100447ae9  jmp     short loc_100447AFA
0x100447aeb  movsd   xmm0, [rsp+3E0h+var_3A0]
0x100447af1  xor     ecx, ecx
0x100447af3  comisd  xmm0, xmm1
0x100447af7  setnbe  cl
0x100447afa  comisd  xmm1, [rsp+3E0h+var_3A8]
0x100447b00  jbe     short loc_100447B07
0x100447b02  mov     eax, r14d
0x100447b05  jmp     short loc_100447B16
0x100447b07  movsd   xmm0, [rsp+3E0h+var_3B0]
0x100447b0d  xor     eax, eax
0x100447b0f  comisd  xmm0, xmm1
0x100447b13  setnbe  al
0x100447b16  test    ecx, ecx
0x100447b18  jz      loc_100447BD3
0x100447b1e  test    eax, eax
0x100447b20  jz      loc_100447BD3
0x100447b26  imul    eax, ecx
0x100447b29  cmp     eax, 1
0x100447b2c  jnz     short loc_100447B49
0x100447b2e  lea     rdx, [rsp+3E0h+var_380]; struct RobustIntersections::CIntegralInterval *
0x100447b33  lea     rcx, [rsp+3E0h+var_3A0]; this
0x100447b38  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100447b3d  lea     rdx, [rsp+3E0h+var_3B0]
0x100447b42  lea     rcx, [rsp+3E0h+var_390]
0x100447b47  jmp     short loc_100447B62
0x100447b49  lea     rdx, [rsp+3E0h+var_3B0]; struct RobustIntersections::CIntegralInterval *
0x100447b4e  lea     rcx, [rsp+3E0h+var_390]; this
0x100447b53  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100447b58  lea     rdx, [rsp+3E0h+var_380]; struct RobustIntersections::CIntegralInterval *
0x100447b5d  lea     rcx, [rsp+3E0h+var_3A0]; this
0x100447b62  mov     r8, rax
0x100447b65  call    ?Multiply@CIntegralInterval@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CIntegralInterval::Multiply(RobustIntersections::CIntegralInterval const &)
0x100447b6a  movsd   xmm2, qword ptr [r8]
0x100447b6f  mov     ecx, 80000000h
0x100447b74  movsd   xmm0, qword ptr [rax+8]
0x100447b79  comisd  xmm0, xmm2
0x100447b7d  jb      short loc_100447BAB
0x100447b7f  movsd   xmm1, qword ptr [rax]
0x100447b83  movsd   xmm3, qword ptr [r8+8]
0x100447b89  comisd  xmm3, xmm1
0x100447b8d  jb      short loc_100447BAB
0x100447b8f  ucomisd xmm1, xmm2
0x100447b93  jp      short loc_100447BB8
0x100447b95  jnz     short loc_100447BB8
0x100447b97  ucomisd xmm0, xmm3
0x100447b9b  jp      short loc_100447BB8
0x100447b9d  jnz     short loc_100447BB8
0x100447b9f  ucomisd xmm0, xmm1
0x100447ba3  jp      short loc_100447BB8
0x100447ba5  jnz     short loc_100447BB8
0x100447ba7  xor     ecx, ecx
0x100447ba9  jmp     short loc_100447BB8
0x100447bab  comisd  xmm2, xmm0
0x100447baf  mov     ecx, 1
0x100447bb4  cmova   ecx, r14d
0x100447bb8  cmp     ecx, 80000000h
0x100447bbe  jz      short loc_100447BD3
0x100447bc0  cmp     ecx, r14d
0x100447bc3  jz      loc_100448125
0x100447bc9  xor     edi, edi
0x100447bcb  cmp     ecx, 1
0x100447bce  jmp     loc_100448121
0x100447bd3  movsd   xmm1, qword ptr [rbx]
0x100447bd7  lea     rcx, [rsp+3E0h+var_370]
0x100447bdc  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447be1  movsd   xmm1, qword ptr [rbx+8]
0x100447be6  lea     rcx, [rbp+2E0h+var_290]
0x100447bea  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447bef  movsd   xmm1, qword ptr [rbx+10h]
0x100447bf4  lea     rcx, [rbp+2E0h+var_178]
0x100447bfb  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447c00  movaps  xmm1, xmm10
0x100447c04  lea     rcx, [rbp+2E0h+var_1B0]
0x100447c0b  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447c10  lea     rdx, [rbp+2E0h+var_1B0]
0x100447c17  lea     rcx, [rsp+3E0h+var_370]
0x100447c1c  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447c21  lea     rdx, [rbp+2E0h+var_178]
0x100447c28  lea     rcx, [rbp+2E0h+var_290]
0x100447c2c  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447c31  neg     [rbp+2E0h+var_28C]
0x100447c34  lea     rdx, [rbp+2E0h+var_290]
0x100447c38  lea     rcx, [rsp+3E0h+var_370]
0x100447c3d  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100447c42  movsd   xmm1, qword ptr [rbx+20h]
0x100447c47  lea     rcx, [rbp+2E0h+var_338]
0x100447c4b  neg     [rbp+2E0h+var_28C]
0x100447c4e  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447c53  movsd   xmm1, qword ptr [rbx+28h]
0x100447c58  lea     rcx, [rbp+2E0h+var_258]
0x100447c5f  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447c64  lea     rdx, [rbp+2E0h+var_1B0]
0x100447c6b  lea     rcx, [rbp+2E0h+var_338]
0x100447c6f  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447c74  lea     rdx, [rbp+2E0h+var_178]
0x100447c7b  lea     rcx, [rbp+2E0h+var_258]
0x100447c82  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447c87  neg     [rbp+2E0h+var_254]
0x100447c8d  lea     rdx, [rbp+2E0h+var_258]
0x100447c94  lea     rcx, [rbp+2E0h+var_338]
0x100447c98  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100447c9d  movsd   xmm1, qword ptr [rbx]
0x100447ca1  lea     rcx, [rbp+2E0h+var_300]
0x100447ca5  neg     [rbp+2E0h+var_254]
0x100447cab  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447cb0  movsd   xmm1, qword ptr [rbx+8]
0x100447cb5  lea     rcx, [rbp+2E0h+var_220]
0x100447cbc  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447cc1  movsd   xmm1, qword ptr [rsi+10h]
0x100447cc6  lea     rcx, [rbp+2E0h+var_108]
0x100447ccd  subsd   xmm1, qword ptr [rsi]
0x100447cd1  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447cd6  movsd   xmm1, qword ptr [rsi+18h]
0x100447cdb  lea     rcx, [rbp+2E0h+var_140]
0x100447ce2  subsd   xmm1, qword ptr [rsi+8]
0x100447ce7  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447cec  lea     rdx, [rbp+2E0h+var_140]
0x100447cf3  lea     rcx, [rbp+2E0h+var_300]
0x100447cf7  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447cfc  lea     rdx, [rbp+2E0h+var_108]
0x100447d03  lea     rcx, [rbp+2E0h+var_220]
0x100447d0a  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447d0f  neg     [rbp+2E0h+var_21C]
0x100447d15  lea     rdx, [rbp+2E0h+var_220]
0x100447d1c  lea     rcx, [rbp+2E0h+var_300]
0x100447d20  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100447d25  movsd   xmm1, qword ptr [rsi]
0x100447d29  lea     rcx, [rbp+2E0h+var_2C8]
0x100447d2d  subsd   xmm1, qword ptr [rbx+30h]
0x100447d32  neg     [rbp+2E0h+var_21C]
0x100447d38  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447d3d  movsd   xmm1, qword ptr [rsi+8]
0x100447d42  lea     rcx, [rbp+2E0h+var_1E8]
0x100447d49  subsd   xmm1, qword ptr [rbx+38h]
0x100447d4e  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x100447d53  lea     rdx, [rbp+2E0h+var_140]
0x100447d5a  lea     rcx, [rbp+2E0h+var_2C8]
0x100447d5e  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447d63  lea     rdx, [rbp+2E0h+var_108]
0x100447d6a  lea     rcx, [rbp+2E0h+var_1E8]
0x100447d71  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x100447d76  neg     [rbp+2E0h+var_1E4]
0x100447d7c  lea     rdx, [rbp+2E0h+var_1E8]
0x100447d83  lea     rcx, [rbp+2E0h+var_2C8]
0x100447d87  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x100447d8c  mov     eax, dword ptr [rsp+3E0h+var_370+4]
0x100447d90  imul    eax, dword ptr [rbp+2E0h+var_300+4]
0x100447d94  neg     [rbp+2E0h+var_1E4]
0x100447d9a  cmp     eax, 1
0x100447d9d  jnz     loc_100447F5F
0x100447da3  mov     edx, dword ptr [rsp+3E0h+var_370]
0x100447da7  mov     r8, [rsp+3E0h+Destination]; int
0x100447dac  lea     rcx, [r8+rdx*4]
0x100447db0  test    edx, edx
0x100447db2  jz      short loc_100447DC3
0x100447db4  cmp     dword ptr [rcx-4], 0
0x100447db8  lea     rcx, [rcx-4]
0x100447dbc  jnz     short loc_100447DC3
0x100447dbe  add     edx, 0FFFFFFFFh
0x100447dc1  jnz     short loc_100447DB4
0x100447dc3  mov     r10, qword ptr [rbp+2E0h+var_2C0]
0x100447dc7  test    edx, edx
0x100447dc9  mov     r9d, 1
0x100447dcf  cmovnz  r9d, edx; unsigned int *
0x100447dd3  mov     edx, dword ptr [rbp+2E0h+var_2C8]
0x100447dd6  lea     rcx, [r10+rdx*4]
0x100447dda  test    edx, edx
0x100447ddc  jz      short loc_100447DEF
0x100447dde  xchg    ax, ax
0x100447de0  cmp     dword ptr [rcx-4], 0
0x100447de4  lea     rcx, [rcx-4]
0x100447de8  jnz     short loc_100447DEF
  ... truncated ...
```
