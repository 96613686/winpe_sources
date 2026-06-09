# RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPairUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x10044a900`
- end: `0x10044aebe`
- name: `?LambdaABSortTransverseIntersectionPairUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `1470`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x10044a130`

## callees

- `0x100401210`
- `0x10042a4e0`
- `0x10042a680`
- `0x10042a7a0`
- `0x10044a900`
- `0x10044b3c0`
- `0x10044b4a0`
- `0x100468a30`
- `0x10046985e`

## pseudocode

```c
__int64 RobustIntersections::CLineSegmentIntersection::LambdaABSortTransverseIntersectionPairUsingExactArithmetic()
{
  __int64 v0; // rbx
  unsigned int *v1; // rax
  unsigned int v2; // esi
  void *v3; // rcx
  size_t v4; // r8
  int v5; // eax
  __int64 v6; // rbx
  unsigned int *v7; // rax
  void *v8; // rcx
  size_t v9; // r8
  int v10; // eax
  __int64 v11; // rbx
  unsigned int *v12; // rax
  void *v13; // rcx
  size_t v14; // r8
  int v15; // eax
  __int64 v16; // rbx
  unsigned int *v17; // rax
  void *v18; // rcx
  size_t v19; // r8
  int v20; // r15d
  int v21; // r12d
  __int64 v22; // rbx
  void *v23; // r10
  int v24; // r14d
  __int64 v25; // rdx
  void *v26; // r13
  __int64 v27; // rdi
  __int64 v28; // r9
  void *v29; // r8
  void *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  void *v33; // r8
  void *v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rdx
  void *v37; // r8
  void *v38; // rcx
  __int64 v39; // r9
  void *v40; // r8
  void *v41; // rcx
  char *i; // rcx
  bool v44; // zf
  __int64 v45; // r9
  __int64 j; // rcx
  int v47; // eax
  unsigned int v48; // ebx
  unsigned int v49; // edx
  char *v50; // rcx
  __int64 v51; // r9
  int v52; // edx
  __int64 v53; // rcx
  int v54; // eax
  unsigned int v55; // ebx
  int v56; // eax
  __int64 v57; // r9
  void *v58; // r8
  __int64 v59; // rdx
  void *v60; // rcx
  unsigned int *v61; // [rsp+28h] [rbp-D8h]
  unsigned int *v62; // [rsp+28h] [rbp-D8h]
  unsigned int v63; // [rsp+30h] [rbp-D0h] BYREF
  int v64; // [rsp+34h] [rbp-CCh]
  void *v65; // [rsp+38h] [rbp-C8h]
  unsigned int v66; // [rsp+68h] [rbp-98h] BYREF
  int v67; // [rsp+6Ch] [rbp-94h]
  void *Destination; // [rsp+70h] [rbp-90h]
  unsigned int v69; // [rsp+A0h] [rbp-60h] BYREF
  int v70; // [rsp+A4h] [rbp-5Ch]
  int v71[12]; // [rsp+A8h] [rbp-58h]
  unsigned int v72; // [rsp+D8h] [rbp-28h] BYREF
  int v73; // [rsp+DCh] [rbp-24h]
  int v74[2]; // [rsp+E0h] [rbp-20h]
  _BYTE v75[56]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v76[56]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v77[56]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v78[56]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v79[56]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v80[56]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v81[56]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v82[56]; // [rsp+298h] [rbp+198h] BYREF
  __int128 Source; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v84; // [rsp+2E0h] [rbp+1E0h]
  __int128 v85; // [rsp+2F0h] [rbp+1F0h]
  __int128 v86; // [rsp+300h] [rbp+200h]
  __int64 v87; // [rsp+310h] [rbp+210h]

  RobustIntersections::CZ<256>::CZ<256>(&v66);
  RobustIntersections::CZ<256>::CZ<256>(v79);
  RobustIntersections::CZ<256>::CZ<256>(v75);
  RobustIntersections::CZ<256>::CZ<256>(v76);
  RobustIntersections::CZ<256>::CZ<256>(&v63);
  RobustIntersections::CZ<256>::CZ<256>(v80);
  RobustIntersections::CZ<256>::CZ<256>(&v69);
  RobustIntersections::CZ<256>::CZ<256>(v81);
  RobustIntersections::CZ<256>::CZ<256>(v77);
  RobustIntersections::CZ<256>::CZ<256>(v78);
  RobustIntersections::CZ<256>::CZ<256>(&v72);
  RobustIntersections::CZ<256>::CZ<256>(v82);
  v0 = RobustIntersections::CZ<128>::Multiply(v79, v75);
  v1 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v66, v76);
  v2 = 0;
  if ( v1 == (unsigned int *)v0 )
  {
    v3 = (void *)*((_QWORD *)v1 + 1);
    v4 = 4LL * *v1;
    v1[1] = 0;
    memset_0(v3, 0, v4);
  }
  else
  {
    *(_DWORD *)(v0 + 4) = -*(_DWORD *)(v0 + 4);
    RobustIntersections::CZ<128>::Add(v1, v0);
    *(_DWORD *)(v0 + 4) = -*(_DWORD *)(v0 + 4);
  }
  v5 = v67;
  if ( v67 == -1 )
    v5 = 1;
  v67 = v5;
  v6 = RobustIntersections::CZ<128>::Multiply(v80, v75);
  v7 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v63, v76);
  if ( v7 == (unsigned int *)v6 )
  {
    v8 = (void *)*((_QWORD *)v7 + 1);
    v9 = 4LL * *v7;
    v7[1] = 0;
    memset_0(v8, 0, v9);
  }
  else
  {
    *(_DWORD *)(v6 + 4) = -*(_DWORD *)(v6 + 4);
    RobustIntersections::CZ<128>::Add(v7, v6);
    *(_DWORD *)(v6 + 4) = -*(_DWORD *)(v6 + 4);
  }
  v10 = v64;
  if ( v64 == -1 )
    v10 = 1;
  v64 = v10;
  v11 = RobustIntersections::CZ<128>::Multiply(v81, v77);
  v12 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v69, v78);
  if ( v12 == (unsigned int *)v11 )
  {
    v13 = (void *)*((_QWORD *)v12 + 1);
    v14 = 4LL * *v12;
    v12[1] = 0;
    memset_0(v13, 0, v14);
  }
  else
  {
    *(_DWORD *)(v11 + 4) = -*(_DWORD *)(v11 + 4);
    RobustIntersections::CZ<128>::Add(v12, v11);
    *(_DWORD *)(v11 + 4) = -*(_DWORD *)(v11 + 4);
  }
  v15 = v70;
  if ( v70 == -1 )
    v15 = 1;
  v70 = v15;
  v16 = RobustIntersections::CZ<128>::Multiply(v82, v77);
  v17 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v72, v78);
  if ( v17 == (unsigned int *)v16 )
  {
    v18 = (void *)*((_QWORD *)v17 + 1);
    v19 = 4LL * *v17;
    v17[1] = 0;
    memset_0(v18, 0, v19);
  }
  else
  {
    *(_DWORD *)(v16 + 4) = -*(_DWORD *)(v16 + 4);
    RobustIntersections::CZ<128>::Add(v17, v16);
    *(_DWORD *)(v16 + 4) = -*(_DWORD *)(v16 + 4);
  }
  v20 = v73;
  v21 = v67;
  v22 = v66;
  if ( v73 == -1 )
    v20 = 1;
  v23 = v65;
  v24 = v64;
  v25 = v63;
  v26 = *(void **)v74;
  v27 = v72;
  v73 = v20;
  if ( v67 > v70 )
    goto LABEL_43;
  if ( v67 >= v70 )
  {
    if ( v67 <= 0 )
    {
      if ( v67 >= 0 )
        goto LABEL_36;
      v29 = Destination;
      v31 = v69;
      v30 = *(void **)v71;
      v28 = v66;
    }
    else
    {
      v28 = v69;
      v29 = *(void **)v71;
      v30 = Destination;
      v31 = v66;
    }
    if ( (unsigned int)RobustIntersections::EaCompare(v30, v31, v29, v28) != -1 )
      goto LABEL_36;
    v23 = v65;
    v25 = v63;
  }
  if ( v24 > v20 )
    return 1;
  if ( v24 >= v20 )
  {
    if ( v24 > 0 )
    {
      v32 = (unsigned int)v27;
      v33 = v26;
      v34 = v23;
      goto LABEL_35;
    }
    if ( v24 < 0 )
    {
      v32 = (unsigned int)v25;
      v33 = v23;
      v25 = (unsigned int)v27;
      v34 = v26;
LABEL_35:
      if ( (unsigned int)RobustIntersections::EaCompare(v34, v25, v33, v32) != 1 )
        goto LABEL_36;
      return 1;
    }
  }
LABEL_36:
  if ( v21 < v70 )
    goto LABEL_52;
  if ( v21 <= 0 )
  {
    if ( v21 >= 0 )
      goto LABEL_52;
    v37 = Destination;
    v35 = (unsigned int)v22;
    v36 = v69;
    v38 = *(void **)v71;
  }
  else
  {
    v35 = v69;
    v36 = (unsigned int)v22;
    v37 = *(void **)v71;
    v38 = Destination;
  }
  if ( (unsigned int)RobustIntersections::EaCompare(v38, v36, v37, v35) != 1 )
    goto LABEL_52;
  v23 = v65;
  v25 = v63;
LABEL_43:
  if ( v24 > v20 )
    goto LABEL_52;
  if ( v24 < v20 )
    return 0xFFFFFFFFLL;
  if ( v24 <= 0 )
  {
    if ( v24 >= 0 )
      goto LABEL_52;
    v39 = (unsigned int)v25;
    v40 = v23;
    v25 = (unsigned int)v27;
    v41 = v26;
  }
  else
  {
    v39 = (unsigned int)v27;
    v40 = v26;
    v41 = v23;
  }
  if ( (unsigned int)RobustIntersections::EaCompare(v41, v25, v40, v39) == -1 )
    return 0xFFFFFFFFLL;
LABEL_52:
  for ( i = (char *)Destination + 4 * v22; (_DWORD)v22; LODWORD(v22) = v22 - 1 )
  {
    v44 = *((_DWORD *)i - 1) == 0;
    i -= 4;
    if ( !v44 )
      break;
  }
  v45 = 1;
  if ( (_DWORD)v22 )
    v45 = (unsigned int)v22;
  for ( j = (__int64)v26 + 4 * v27; (_DWORD)v27; LODWORD(v27) = v27 - 1 )
  {
    v44 = *(_DWORD *)(j - 4) == 0;
    j -= 4;
    if ( !v44 )
      break;
  }
  v47 = 1;
  Source = 0;
  if ( (_DWORD)v27 )
    v47 = v27;
  v87 = 0;
  LODWORD(v61) = v47;
  v84 = 0;
  v48 = v47 + v45;
  v85 = 0;
  v86 = 0;
  RobustIntersections::EaMultiply(
    (RobustIntersections *)&Source,
    (unsigned int *)(unsigned int)(v47 + v45),
    (int)Destination,
    (const unsigned int *)v45,
    (int)v26,
    v61,
    v63);
  memcpy_s(Destination, 4LL * v48, &Source, 4LL * v48);
  v49 = v63;
  v67 *= v73;
  v50 = (char *)v65 + 4 * v63;
  if ( v63 )
  {
    do
    {
      v44 = *((_DWORD *)v50 - 1) == 0;
      v50 -= 4;
      if ( !v44 )
        break;
      --v49;
    }
    while ( v49 );
  }
  v51 = 1;
  if ( v49 )
    v51 = v49;
  v52 = v69;
  v53 = *(_QWORD *)v71 + 4LL * v69;
  if ( v69 )
  {
    do
    {
      v44 = *(_DWORD *)(v53 - 4) == 0;
      v53 -= 4;
      if ( !v44 )
        break;
      --v52;
    }
    while ( v52 );
  }
  v54 = 1;
  if ( v52 )
    v54 = v52;
  v87 = 0;
  LODWORD(v62) = v54;
  Source = 0;
  v55 = v54 + v51;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  RobustIntersections::EaMultiply(
    (RobustIntersections *)&Source,
    (unsigned int *)(unsigned int)(v54 + v51),
    (int)v65,
    (const unsigned int *)v51,
    v71[0],
    v62,
    v63);
  memcpy_s(v65, 4LL * v55, &Source, 4LL * v55);
  v56 = v64 * v70;
  v64 = v56;
  if ( v56 <= v67 )
  {
    if ( v56 >= v67 )
    {
      if ( v56 <= 0 )
      {
        if ( v56 >= 0 )
          return v2;
        v57 = v63;
        v58 = v65;
        v59 = v66;
        v60 = Destination;
      }
      else
      {
        v57 = v66;
        v58 = Destination;
        v59 = v63;
        v60 = v65;
      }
      return (unsigned int)RobustIntersections::EaCompare(v60, v59, v58, v57);
    }
    return (unsigned int)-1;
  }
  else
  {
    return 1;
  }
}

```

## disassembly

```asm
0x10044a900  mov     [rsp-8+arg_0], rbx
0x10044a905  mov     [rsp-8+arg_8], rsi
0x10044a90a  mov     [rsp-8+arg_10], rdi
0x10044a90f  push    rbp
0x10044a910  push    r12
0x10044a912  push    r13
0x10044a914  push    r14
0x10044a916  push    r15
0x10044a918  lea     rbp, [rsp-230h]
0x10044a920  sub     rsp, 330h
0x10044a927  mov     rax, cs:__security_cookie
0x10044a92e  xor     rax, rsp
0x10044a931  mov     [rbp+250h+var_30], rax
0x10044a938  movsd   xmm1, qword ptr [rcx]
0x10044a93c  mov     r9, rcx
0x10044a93f  lea     rcx, [rsp+350h+var_2E8]
0x10044a944  mov     r10, rdx
0x10044a947  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a94c  movsd   xmm1, qword ptr [r9+8]
0x10044a952  lea     rcx, [rbp+250h+var_160]
0x10044a959  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a95e  movsd   xmm1, qword ptr [r9+10h]
0x10044a964  lea     rcx, [rbp+250h+var_240]
0x10044a968  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a96d  movsd   xmm1, qword ptr [r9+18h]
0x10044a973  lea     rcx, [rbp+250h+var_208]
0x10044a977  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a97c  movsd   xmm1, qword ptr [r9+20h]
0x10044a982  lea     rcx, [rsp+350h+var_320]
0x10044a987  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a98c  movsd   xmm1, qword ptr [r9+28h]
0x10044a992  lea     rcx, [rbp+250h+var_128]
0x10044a999  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a99e  movsd   xmm1, qword ptr [r10]
0x10044a9a3  lea     rcx, [rbp+250h+var_2B0]
0x10044a9a7  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a9ac  movsd   xmm1, qword ptr [r10+8]
0x10044a9b2  lea     rcx, [rbp+250h+var_F0]
0x10044a9b9  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a9be  movsd   xmm1, qword ptr [r10+10h]
0x10044a9c4  lea     rcx, [rbp+250h+var_1D0]
0x10044a9cb  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a9d0  movsd   xmm1, qword ptr [r10+18h]
0x10044a9d6  lea     rcx, [rbp+250h+var_198]
0x10044a9dd  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a9e2  movsd   xmm1, qword ptr [r10+20h]
0x10044a9e8  lea     rcx, [rbp+250h+var_278]
0x10044a9ec  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044a9f1  movsd   xmm1, qword ptr [r10+28h]
0x10044a9f7  lea     rcx, [rbp+250h+var_B8]
0x10044a9fe  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044aa03  lea     rdx, [rbp+250h+var_240]
0x10044aa07  lea     rcx, [rbp+250h+var_160]
0x10044aa0e  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044aa13  lea     rdx, [rbp+250h+var_208]
0x10044aa17  mov     rbx, rax
0x10044aa1a  lea     rcx, [rsp+350h+var_2E8]
0x10044aa1f  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044aa24  xor     esi, esi
0x10044aa26  mov     rcx, rax
0x10044aa29  cmp     rax, rbx
0x10044aa2c  jnz     short loc_10044AA45
0x10044aa2e  mov     r8d, [rax]
0x10044aa31  xor     edx, edx; Val
0x10044aa33  mov     rcx, [rax+8]; void *
0x10044aa37  shl     r8, 2; Size
0x10044aa3b  mov     [rax+4], esi
0x10044aa3e  call    memset_0
0x10044aa43  jmp     short loc_10044AA5D
0x10044aa45  mov     eax, [rbx+4]
0x10044aa48  mov     rdx, rbx
0x10044aa4b  neg     eax
0x10044aa4d  mov     [rbx+4], eax
0x10044aa50  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044aa55  mov     eax, [rbx+4]
0x10044aa58  neg     eax
0x10044aa5a  mov     [rbx+4], eax
0x10044aa5d  mov     eax, dword ptr [rsp+350h+var_2E8+4]
0x10044aa61  lea     rdx, [rbp+250h+var_240]
0x10044aa65  cmp     eax, 0FFFFFFFFh
0x10044aa68  lea     rcx, [rbp+250h+var_128]
0x10044aa6f  mov     edi, 1
0x10044aa74  cmovz   eax, edi
0x10044aa77  mov     dword ptr [rsp+350h+var_2E8+4], eax
0x10044aa7b  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044aa80  lea     rdx, [rbp+250h+var_208]
0x10044aa84  mov     rbx, rax
0x10044aa87  lea     rcx, [rsp+350h+var_320]
0x10044aa8c  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044aa91  mov     rcx, rax
0x10044aa94  cmp     rax, rbx
0x10044aa97  jnz     short loc_10044AAB0
0x10044aa99  mov     r8d, [rax]
0x10044aa9c  xor     edx, edx; Val
0x10044aa9e  mov     rcx, [rax+8]; void *
0x10044aaa2  shl     r8, 2; Size
0x10044aaa6  mov     [rax+4], esi
0x10044aaa9  call    memset_0
0x10044aaae  jmp     short loc_10044AAC8
0x10044aab0  mov     eax, [rbx+4]
0x10044aab3  mov     rdx, rbx
0x10044aab6  neg     eax
0x10044aab8  mov     [rbx+4], eax
0x10044aabb  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044aac0  mov     eax, [rbx+4]
0x10044aac3  neg     eax
0x10044aac5  mov     [rbx+4], eax
0x10044aac8  mov     eax, dword ptr [rsp+350h+var_320+4]
0x10044aacc  lea     rdx, [rbp+250h+var_1D0]
0x10044aad3  cmp     eax, 0FFFFFFFFh
0x10044aad6  lea     rcx, [rbp+250h+var_F0]
0x10044aadd  cmovz   eax, edi
0x10044aae0  mov     dword ptr [rsp+350h+var_320+4], eax
0x10044aae4  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044aae9  lea     rdx, [rbp+250h+var_198]
0x10044aaf0  mov     rbx, rax
0x10044aaf3  lea     rcx, [rbp+250h+var_2B0]
0x10044aaf7  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044aafc  mov     rcx, rax
0x10044aaff  cmp     rax, rbx
0x10044ab02  jnz     short loc_10044AB1B
0x10044ab04  mov     r8d, [rax]
0x10044ab07  xor     edx, edx; Val
0x10044ab09  mov     rcx, [rax+8]; void *
0x10044ab0d  shl     r8, 2; Size
0x10044ab11  mov     [rax+4], esi
0x10044ab14  call    memset_0
0x10044ab19  jmp     short loc_10044AB33
0x10044ab1b  mov     eax, [rbx+4]
0x10044ab1e  mov     rdx, rbx
0x10044ab21  neg     eax
0x10044ab23  mov     [rbx+4], eax
0x10044ab26  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044ab2b  mov     eax, [rbx+4]
0x10044ab2e  neg     eax
0x10044ab30  mov     [rbx+4], eax
0x10044ab33  mov     eax, dword ptr [rbp+250h+var_2B0+4]
0x10044ab36  lea     rdx, [rbp+250h+var_1D0]
0x10044ab3d  cmp     eax, 0FFFFFFFFh
0x10044ab40  lea     rcx, [rbp+250h+var_B8]
0x10044ab47  cmovz   eax, edi
0x10044ab4a  mov     dword ptr [rbp+250h+var_2B0+4], eax
0x10044ab4d  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044ab52  lea     rdx, [rbp+250h+var_198]
0x10044ab59  mov     rbx, rax
0x10044ab5c  lea     rcx, [rbp+250h+var_278]
0x10044ab60  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044ab65  mov     rcx, rax
0x10044ab68  cmp     rax, rbx
0x10044ab6b  jnz     short loc_10044AB84
0x10044ab6d  mov     r8d, [rax]
0x10044ab70  xor     edx, edx; Val
0x10044ab72  mov     rcx, [rax+8]; void *
0x10044ab76  shl     r8, 2; Size
0x10044ab7a  mov     [rax+4], esi
0x10044ab7d  call    memset_0
0x10044ab82  jmp     short loc_10044AB9C
0x10044ab84  mov     eax, [rbx+4]
0x10044ab87  mov     rdx, rbx
0x10044ab8a  neg     eax
0x10044ab8c  mov     [rbx+4], eax
0x10044ab8f  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044ab94  mov     eax, [rbx+4]
0x10044ab97  neg     eax
0x10044ab99  mov     [rbx+4], eax
0x10044ab9c  mov     r15d, dword ptr [rbp+250h+var_278+4]
0x10044aba0  cmp     r15d, 0FFFFFFFFh
0x10044aba4  mov     r12d, dword ptr [rsp+350h+var_2E8+4]
0x10044aba9  mov     ebx, dword ptr [rsp+350h+var_2E8]
0x10044abad  cmovz   r15d, edi
0x10044abb1  mov     r10, [rsp+350h+var_318]
0x10044abb6  mov     r14d, dword ptr [rsp+350h+var_320+4]
0x10044abbb  mov     edx, dword ptr [rsp+350h+var_320]
0x10044abbf  mov     r13, qword ptr [rbp+250h+var_270]
0x10044abc3  mov     edi, dword ptr [rbp+250h+var_278]
0x10044abc6  mov     dword ptr [rbp+250h+var_278+4], r15d
0x10044abca  cmp     r12d, dword ptr [rbp+250h+var_2B0+4]
0x10044abce  jg      loc_10044AC85
0x10044abd4  mov     rax, qword ptr [rbp+250h+var_2A8]
0x10044abd8  mov     ecx, dword ptr [rbp+250h+var_2B0]
0x10044abdb  jl      short loc_10044AC13
0x10044abdd  test    r12d, r12d
0x10044abe0  jle     short loc_10044ABF1
0x10044abe2  mov     r9d, ecx
0x10044abe5  mov     r8, rax
0x10044abe8  mov     rcx, [rsp+350h+Destination]
0x10044abed  mov     edx, ebx
0x10044abef  jmp     short loc_10044AC00
0x10044abf1  jns     short loc_10044AC45
0x10044abf3  mov     r8, [rsp+350h+Destination]
0x10044abf8  mov     edx, ecx
0x10044abfa  mov     rcx, rax
0x10044abfd  mov     r9d, ebx
0x10044ac00  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044ac05  cmp     eax, 0FFFFFFFFh
0x10044ac08  jnz     short loc_10044AC45
0x10044ac0a  mov     r10, [rsp+350h+var_318]
0x10044ac0f  mov     edx, dword ptr [rsp+350h+var_320]
0x10044ac13  cmp     r14d, r15d
0x10044ac16  jg      loc_10044AC9C
0x10044ac1c  jl      short loc_10044AC45
0x10044ac1e  test    r14d, r14d
0x10044ac21  jle     short loc_10044AC2E
0x10044ac23  mov     r9d, edi
0x10044ac26  mov     r8, r13
0x10044ac29  mov     rcx, r10
0x10044ac2c  jmp     short loc_10044AC3B
0x10044ac2e  jns     short loc_10044AC45
0x10044ac30  mov     r9d, edx
0x10044ac33  mov     r8, r10
0x10044ac36  mov     edx, edi
0x10044ac38  mov     rcx, r13
0x10044ac3b  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044ac40  cmp     eax, 1
0x10044ac43  jz      short loc_10044AC9C
0x10044ac45  cmp     r12d, dword ptr [rbp+250h+var_2B0+4]
0x10044ac49  jl      short loc_10044ACC7
0x10044ac4b  test    r12d, r12d
0x10044ac4e  jle     short loc_10044AC61
0x10044ac50  mov     r9d, dword ptr [rbp+250h+var_2B0]
0x10044ac54  mov     edx, ebx
0x10044ac56  mov     r8, qword ptr [rbp+250h+var_2A8]
0x10044ac5a  mov     rcx, [rsp+350h+Destination]
0x10044ac5f  jmp     short loc_10044AC72
0x10044ac61  jns     short loc_10044ACC7
0x10044ac63  mov     r8, [rsp+350h+Destination]
0x10044ac68  mov     r9d, ebx
0x10044ac6b  mov     edx, dword ptr [rbp+250h+var_2B0]
0x10044ac6e  mov     rcx, qword ptr [rbp+250h+var_2A8]
0x10044ac72  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044ac77  cmp     eax, 1
0x10044ac7a  jnz     short loc_10044ACC7
0x10044ac7c  mov     r10, [rsp+350h+var_318]
0x10044ac81  mov     edx, dword ptr [rsp+350h+var_320]
0x10044ac85  cmp     r14d, r15d
0x10044ac88  jg      short loc_10044ACC7
0x10044ac8a  jl      short loc_10044ACBD
0x10044ac8c  test    r14d, r14d
0x10044ac8f  jle     short loc_10044ACA6
0x10044ac91  mov     r9d, edi
0x10044ac94  mov     r8, r13
0x10044ac97  mov     rcx, r10
0x10044ac9a  jmp     short loc_10044ACB3
0x10044ac9c  mov     eax, 1
0x10044aca1  jmp     loc_10044AE8E
0x10044aca6  jns     short loc_10044ACC7
0x10044aca8  mov     r9d, edx
0x10044acab  mov     r8, r10
0x10044acae  mov     edx, edi
0x10044acb0  mov     rcx, r13
0x10044acb3  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044acb8  cmp     eax, 0FFFFFFFFh
0x10044acbb  jnz     short loc_10044ACC7
0x10044acbd  mov     eax, 0FFFFFFFFh
0x10044acc2  jmp     loc_10044AE8E
0x10044acc7  mov     rdx, [rsp+350h+Destination]
0x10044accc  lea     rcx, [rdx+rbx*4]
0x10044acd0  test    ebx, ebx
0x10044acd2  jz      short loc_10044ACE2
0x10044acd4  cmp     [rcx-4], esi
0x10044acd7  lea     rcx, [rcx-4]
0x10044acdb  jnz     short loc_10044ACE2
0x10044acdd  add     ebx, 0FFFFFFFFh
0x10044ace0  jnz     short loc_10044ACD4
0x10044ace2  test    ebx, ebx
0x10044ace4  lea     rcx, ds:0[rdi*4]
0x10044acec  mov     r9d, 1
0x10044acf2  cmovnz  r9d, ebx; unsigned int *
0x10044acf6  add     rcx, r13
0x10044acf9  test    edi, edi
0x10044acfb  jz      short loc_10044AD0E
0x10044acfd  nop     dword ptr [rax]
0x10044ad00  cmp     [rcx-4], esi
0x10044ad03  lea     rcx, [rcx-4]
0x10044ad07  jnz     short loc_10044AD0E
0x10044ad09  add     edi, 0FFFFFFFFh
0x10044ad0c  jnz     short loc_10044AD00
0x10044ad0e  xorps   xmm0, xmm0
0x10044ad11  mov     eax, 1
0x10044ad16  mov     r8, rdx; int
0x10044ad19  test    edi, edi
0x10044ad1b  movups  [rbp+250h+Source], xmm0
0x10044ad22  cmovnz  eax, edi
0x10044ad25  xor     ecx, ecx
0x10044ad27  mov     [rbp+250h+var_40], rcx
0x10044ad2e  lea     rcx, [rbp+250h+Source]; this
0x10044ad35  mov     dword ptr [rsp+350h+var_328], eax; unsigned int *
0x10044ad39  movups  [rbp+250h+var_70], xmm0
0x10044ad40  lea     ebx, [rax+r9]
0x10044ad44  mov     qword ptr [rsp+350h+var_330], r13; int
0x10044ad49  mov     edx, ebx; unsigned int *
0x10044ad4b  movups  [rbp+250h+var_60], xmm0
0x10044ad52  movups  [rbp+250h+var_50], xmm0
0x10044ad59  call    ?EaMultiply@RobustIntersections@@YAIPEAIHPEBIH1H@Z; RobustIntersections::EaMultiply(uint *,int,uint const *,int,uint const *,int)
0x10044ad5e  mov     rcx, [rsp+350h+Destination]; Destination
0x10044ad63  lea     r8, [rbp+250h+Source]; Source
0x10044ad6a  mov     edx, ebx
0x10044ad6c  shl     rdx, 2; DestinationSize
0x10044ad70  mov     r9, rdx; SourceSize
0x10044ad73  call    memcpy_s
  ... truncated ...
```
