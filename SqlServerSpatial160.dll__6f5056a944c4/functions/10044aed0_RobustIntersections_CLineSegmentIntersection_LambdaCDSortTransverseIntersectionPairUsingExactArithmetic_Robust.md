# RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPairUsingExactArithmetic(RobustIntersections::CLineSegmentIntersection const &,RobustIntersections::CLineSegmentIntersection const &)

- ea: `0x10044aed0`
- end: `0x10044b3ac`
- name: `?LambdaCDSortTransverseIntersectionPairUsingExactArithmetic@CLineSegmentIntersection@RobustIntersections@@CA?AW4COMPARISON@2@AEBV12@0@Z`
- size: `1244`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x10044a510`

## callees

- `0x100401210`
- `0x10042a4e0`
- `0x10042a680`
- `0x10042a7a0`
- `0x10044aed0`
- `0x10044b3c0`
- `0x10044b4a0`
- `0x100468a30`
- `0x10046985e`

## pseudocode

```c
__int64 RobustIntersections::CLineSegmentIntersection::LambdaCDSortTransverseIntersectionPairUsingExactArithmetic()
{
  __int64 v0; // rbx
  unsigned int *v1; // rax
  unsigned int v2; // edi
  void *v3; // rcx
  size_t v4; // r8
  __int64 v5; // rbx
  unsigned int *v6; // rax
  void *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rbx
  unsigned int *v10; // rax
  void *v11; // rcx
  size_t v12; // r8
  __int64 v13; // rbx
  unsigned int *v14; // rax
  void *v15; // rcx
  size_t v16; // r8
  unsigned int v17; // edx
  char *i; // rcx
  bool v19; // zf
  __int64 v20; // r9
  int v21; // edx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // edx
  char *v26; // rcx
  __int64 v27; // r9
  int v28; // edx
  __int64 v29; // rcx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int *v33; // rbx
  unsigned int *v34; // rax
  int v35; // ecx
  __int64 v36; // r9
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rcx
  unsigned int *v41; // [rsp+28h] [rbp-D8h]
  unsigned int *v42; // [rsp+28h] [rbp-D8h]
  unsigned int v43; // [rsp+30h] [rbp-D0h] BYREF
  int v44; // [rsp+34h] [rbp-CCh]
  void *Destination; // [rsp+38h] [rbp-C8h]
  unsigned int v46; // [rsp+68h] [rbp-98h] BYREF
  int v47; // [rsp+6Ch] [rbp-94h]
  void *v48; // [rsp+70h] [rbp-90h]
  unsigned int v49; // [rsp+A0h] [rbp-60h] BYREF
  int v50; // [rsp+A4h] [rbp-5Ch]
  int v51[12]; // [rsp+A8h] [rbp-58h]
  unsigned int v52; // [rsp+D8h] [rbp-28h] BYREF
  int v53; // [rsp+DCh] [rbp-24h]
  int v54[12]; // [rsp+E0h] [rbp-20h]
  _BYTE v55[56]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v56[56]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v57[56]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v58[56]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v59[56]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v60[56]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v61[56]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v62[56]; // [rsp+298h] [rbp+198h] BYREF
  __int128 Source; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v64; // [rsp+2E0h] [rbp+1E0h]
  __int128 v65; // [rsp+2F0h] [rbp+1F0h]
  __int128 v66; // [rsp+300h] [rbp+200h]
  __int64 v67; // [rsp+310h] [rbp+210h]

  RobustIntersections::CZ<256>::CZ<256>(v56);
  RobustIntersections::CZ<256>::CZ<256>(v55);
  RobustIntersections::CZ<256>::CZ<256>(v59);
  RobustIntersections::CZ<256>::CZ<256>(&v46);
  RobustIntersections::CZ<256>::CZ<256>(v60);
  RobustIntersections::CZ<256>::CZ<256>(&v49);
  RobustIntersections::CZ<256>::CZ<256>(v58);
  RobustIntersections::CZ<256>::CZ<256>(v57);
  RobustIntersections::CZ<256>::CZ<256>(v61);
  RobustIntersections::CZ<256>::CZ<256>(&v43);
  RobustIntersections::CZ<256>::CZ<256>(v62);
  RobustIntersections::CZ<256>::CZ<256>(&v52);
  v0 = RobustIntersections::CZ<128>::Multiply(v59, v55);
  v1 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v46, v56);
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
  v5 = RobustIntersections::CZ<128>::Multiply(v60, v55);
  v6 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v49, v56);
  if ( v6 == (unsigned int *)v5 )
  {
    v7 = (void *)*((_QWORD *)v6 + 1);
    v8 = 4LL * *v6;
    v6[1] = 0;
    memset_0(v7, 0, v8);
  }
  else
  {
    *(_DWORD *)(v5 + 4) = -*(_DWORD *)(v5 + 4);
    RobustIntersections::CZ<128>::Add(v6, v5);
    *(_DWORD *)(v5 + 4) = -*(_DWORD *)(v5 + 4);
  }
  v9 = RobustIntersections::CZ<128>::Multiply(v61, v57);
  v10 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v43, v58);
  if ( v10 == (unsigned int *)v9 )
  {
    v11 = (void *)*((_QWORD *)v10 + 1);
    v12 = 4LL * *v10;
    v10[1] = 0;
    memset_0(v11, 0, v12);
  }
  else
  {
    *(_DWORD *)(v9 + 4) = -*(_DWORD *)(v9 + 4);
    RobustIntersections::CZ<128>::Add(v10, v9);
    *(_DWORD *)(v9 + 4) = -*(_DWORD *)(v9 + 4);
  }
  v13 = RobustIntersections::CZ<128>::Multiply(v62, v57);
  v14 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v52, v58);
  if ( v14 == (unsigned int *)v13 )
  {
    v15 = (void *)*((_QWORD *)v14 + 1);
    v16 = 4LL * *v14;
    v14[1] = 0;
    memset_0(v15, 0, v16);
  }
  else
  {
    *(_DWORD *)(v13 + 4) = -*(_DWORD *)(v13 + 4);
    RobustIntersections::CZ<128>::Add(v14, v13);
    *(_DWORD *)(v13 + 4) = -*(_DWORD *)(v13 + 4);
  }
  if ( v53 * v50 == -1 )
  {
    v17 = v43;
    for ( i = (char *)Destination + 4 * v43; v17; --v17 )
    {
      v19 = *((_DWORD *)i - 1) == 0;
      i -= 4;
      if ( !v19 )
        break;
    }
    v20 = 1;
    if ( v17 )
      v20 = v17;
    v21 = v49;
    v22 = *(_QWORD *)v51 + 4LL * v49;
    if ( v49 )
    {
      do
      {
        v19 = *(_DWORD *)(v22 - 4) == 0;
        v22 -= 4;
        if ( !v19 )
          break;
        --v21;
      }
      while ( v21 );
    }
    v23 = 1;
    if ( v21 )
      v23 = v21;
    v67 = 0;
    LODWORD(v41) = v23;
    Source = 0;
    v24 = v23 + v20;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    RobustIntersections::EaMultiply(
      (RobustIntersections *)&Source,
      (unsigned int *)(unsigned int)(v23 + v20),
      (int)Destination,
      (const unsigned int *)v20,
      v51[0],
      v41,
      v43);
    memcpy_s(Destination, 4LL * v24, &Source, 4LL * v24);
    v25 = v46;
    v44 *= v50;
    v26 = (char *)v48 + 4 * v46;
    if ( v46 )
    {
      do
      {
        v19 = *((_DWORD *)v26 - 1) == 0;
        v26 -= 4;
        if ( !v19 )
          break;
        --v25;
      }
      while ( v25 );
    }
    v27 = 1;
    if ( v25 )
      v27 = v25;
    v28 = v52;
    v29 = *(_QWORD *)v54 + 4LL * v52;
    if ( v52 )
    {
      do
      {
        v19 = *(_DWORD *)(v29 - 4) == 0;
        v29 -= 4;
        if ( !v19 )
          break;
        --v28;
      }
      while ( v28 );
    }
    v30 = 1;
    if ( v28 )
      v30 = v28;
    v67 = 0;
    LODWORD(v42) = v30;
    Source = 0;
    v31 = v30 + v27;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    RobustIntersections::EaMultiply(
      (RobustIntersections *)&Source,
      (unsigned int *)(unsigned int)(v30 + v27),
      (int)v48,
      (const unsigned int *)v27,
      v54[0],
      v42,
      v43);
    memcpy_s(v48, 4LL * v31, &Source, 4LL * v31);
    v32 = v53 * v47;
    v47 = v32;
    if ( v32 <= v44 )
    {
      if ( v32 >= v44 )
      {
        if ( v32 <= 0 )
        {
          if ( v32 < 0 )
            v2 = RobustIntersections::EaCompare(Destination, v43, v48, v46);
          return -v2;
        }
        else
        {
          return (unsigned int)-(int)RobustIntersections::EaCompare(v48, v46, Destination, v43);
        }
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return (unsigned int)-1;
    }
  }
  else
  {
    v33 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v43, &v49);
    v34 = (unsigned int *)RobustIntersections::CZ<128>::Multiply(&v46, &v52);
    v35 = v34[1];
    if ( v35 <= (int)v33[1] )
    {
      if ( v35 >= (int)v33[1] )
      {
        if ( v35 <= 0 )
        {
          if ( v35 >= 0 )
            return v2;
          v36 = *v34;
          v37 = *((_QWORD *)v34 + 1);
          v38 = *v33;
          v39 = *((_QWORD *)v33 + 1);
        }
        else
        {
          v36 = *v33;
          v37 = *((_QWORD *)v33 + 1);
          v38 = *v34;
          v39 = *((_QWORD *)v34 + 1);
        }
        return (unsigned int)RobustIntersections::EaCompare(v39, v38, v37, v36);
      }
      return (unsigned int)-1;
    }
    else
    {
      return 1;
    }
  }
}

```

## disassembly

```asm
0x10044aed0  mov     [rsp-8+arg_0], rbx
0x10044aed5  mov     [rsp-8+arg_8], rdi
0x10044aeda  push    rbp
0x10044aedb  lea     rbp, [rsp-230h]
0x10044aee3  sub     rsp, 330h
0x10044aeea  mov     rax, cs:__security_cookie
0x10044aef1  xor     rax, rsp
0x10044aef4  mov     [rbp+230h+var_10], rax
0x10044aefb  movsd   xmm1, qword ptr [rcx]
0x10044aeff  mov     r9, rcx
0x10044af02  lea     rcx, [rbp+230h+var_1E8]
0x10044af06  mov     r10, rdx
0x10044af09  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af0e  movsd   xmm1, qword ptr [r9+8]
0x10044af14  lea     rcx, [rbp+230h+var_220]
0x10044af18  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af1d  movsd   xmm1, qword ptr [r9+20h]
0x10044af23  lea     rcx, [rbp+230h+var_140]
0x10044af2a  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af2f  movsd   xmm1, qword ptr [r9+28h]
0x10044af35  lea     rcx, [rsp+330h+var_2C8]
0x10044af3a  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af3f  movsd   xmm1, qword ptr [r9+10h]
0x10044af45  lea     rcx, [rbp+230h+var_108]
0x10044af4c  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af51  movsd   xmm1, qword ptr [r9+18h]
0x10044af57  lea     rcx, [rbp+230h+var_290]
0x10044af5b  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af60  movsd   xmm1, qword ptr [r10]
0x10044af65  lea     rcx, [rbp+230h+var_178]
0x10044af6c  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af71  movsd   xmm1, qword ptr [r10+8]
0x10044af77  lea     rcx, [rbp+230h+var_1B0]
0x10044af7e  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af83  movsd   xmm1, qword ptr [r10+20h]
0x10044af89  lea     rcx, [rbp+230h+var_D0]
0x10044af90  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044af95  movsd   xmm1, qword ptr [r10+28h]
0x10044af9b  lea     rcx, [rsp+330h+var_300]
0x10044afa0  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044afa5  movsd   xmm1, qword ptr [r10+10h]
0x10044afab  lea     rcx, [rbp+230h+var_98]
0x10044afb2  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044afb7  movsd   xmm1, qword ptr [r10+18h]
0x10044afbd  lea     rcx, [rbp+230h+var_258]
0x10044afc1  call    ??0?$CZ@$0BAA@@RobustIntersections@@QEAA@N@Z; RobustIntersections::CZ<256>::CZ<256>(double)
0x10044afc6  lea     rdx, [rbp+230h+var_220]
0x10044afca  lea     rcx, [rbp+230h+var_140]
0x10044afd1  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044afd6  lea     rdx, [rbp+230h+var_1E8]
0x10044afda  mov     rbx, rax
0x10044afdd  lea     rcx, [rsp+330h+var_2C8]
0x10044afe2  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044afe7  xor     edi, edi
0x10044afe9  mov     rcx, rax
0x10044afec  cmp     rax, rbx
0x10044afef  jnz     short loc_10044B008
0x10044aff1  mov     r8d, [rax]
0x10044aff4  xor     edx, edx; Val
0x10044aff6  mov     rcx, [rax+8]; void *
0x10044affa  shl     r8, 2; Size
0x10044affe  mov     [rax+4], edi
0x10044b001  call    memset_0
0x10044b006  jmp     short loc_10044B020
0x10044b008  mov     eax, [rbx+4]
0x10044b00b  mov     rdx, rbx
0x10044b00e  neg     eax
0x10044b010  mov     [rbx+4], eax
0x10044b013  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044b018  mov     eax, [rbx+4]
0x10044b01b  neg     eax
0x10044b01d  mov     [rbx+4], eax
0x10044b020  lea     rdx, [rbp+230h+var_220]
0x10044b024  lea     rcx, [rbp+230h+var_108]
0x10044b02b  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b030  lea     rdx, [rbp+230h+var_1E8]
0x10044b034  mov     rbx, rax
0x10044b037  lea     rcx, [rbp+230h+var_290]
0x10044b03b  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b040  mov     rcx, rax
0x10044b043  cmp     rax, rbx
0x10044b046  jnz     short loc_10044B05F
0x10044b048  mov     r8d, [rax]
0x10044b04b  xor     edx, edx; Val
0x10044b04d  mov     rcx, [rax+8]; void *
0x10044b051  shl     r8, 2; Size
0x10044b055  mov     [rax+4], edi
0x10044b058  call    memset_0
0x10044b05d  jmp     short loc_10044B077
0x10044b05f  mov     eax, [rbx+4]
0x10044b062  mov     rdx, rbx
0x10044b065  neg     eax
0x10044b067  mov     [rbx+4], eax
0x10044b06a  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044b06f  mov     eax, [rbx+4]
0x10044b072  neg     eax
0x10044b074  mov     [rbx+4], eax
0x10044b077  lea     rdx, [rbp+230h+var_1B0]
0x10044b07e  lea     rcx, [rbp+230h+var_D0]
0x10044b085  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b08a  lea     rdx, [rbp+230h+var_178]
0x10044b091  mov     rbx, rax
0x10044b094  lea     rcx, [rsp+330h+var_300]
0x10044b099  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b09e  mov     rcx, rax
0x10044b0a1  cmp     rax, rbx
0x10044b0a4  jnz     short loc_10044B0BD
0x10044b0a6  mov     r8d, [rax]
0x10044b0a9  xor     edx, edx; Val
0x10044b0ab  mov     rcx, [rax+8]; void *
0x10044b0af  shl     r8, 2; Size
0x10044b0b3  mov     [rax+4], edi
0x10044b0b6  call    memset_0
0x10044b0bb  jmp     short loc_10044B0D5
0x10044b0bd  mov     eax, [rbx+4]
0x10044b0c0  mov     rdx, rbx
0x10044b0c3  neg     eax
0x10044b0c5  mov     [rbx+4], eax
0x10044b0c8  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044b0cd  mov     eax, [rbx+4]
0x10044b0d0  neg     eax
0x10044b0d2  mov     [rbx+4], eax
0x10044b0d5  lea     rdx, [rbp+230h+var_1B0]
0x10044b0dc  lea     rcx, [rbp+230h+var_98]
0x10044b0e3  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b0e8  lea     rdx, [rbp+230h+var_178]
0x10044b0ef  mov     rbx, rax
0x10044b0f2  lea     rcx, [rbp+230h+var_258]
0x10044b0f6  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b0fb  mov     rcx, rax
0x10044b0fe  cmp     rax, rbx
0x10044b101  jnz     short loc_10044B11A
0x10044b103  mov     r8d, [rax]
0x10044b106  xor     edx, edx; Val
0x10044b108  mov     rcx, [rax+8]; void *
0x10044b10c  shl     r8, 2; Size
0x10044b110  mov     [rax+4], edi
0x10044b113  call    memset_0
0x10044b118  jmp     short loc_10044B132
0x10044b11a  mov     eax, [rbx+4]
0x10044b11d  mov     rdx, rbx
0x10044b120  neg     eax
0x10044b122  mov     [rbx+4], eax
0x10044b125  call    ?Add@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Add(RobustIntersections::CZ<128> const &)
0x10044b12a  mov     eax, [rbx+4]
0x10044b12d  neg     eax
0x10044b12f  mov     [rbx+4], eax
0x10044b132  mov     eax, dword ptr [rbp+230h+var_290+4]
0x10044b135  imul    eax, dword ptr [rbp+230h+var_258+4]
0x10044b139  cmp     eax, 0FFFFFFFFh
0x10044b13c  jnz     loc_10044B326
0x10044b142  mov     edx, dword ptr [rsp+330h+var_300]
0x10044b146  mov     r8, [rsp+330h+Destination]; int
0x10044b14b  lea     rcx, [r8+rdx*4]
0x10044b14f  test    edx, edx
0x10044b151  jz      short loc_10044B161
0x10044b153  cmp     [rcx-4], edi
0x10044b156  lea     rcx, [rcx-4]
0x10044b15a  jnz     short loc_10044B161
0x10044b15c  add     edx, 0FFFFFFFFh
0x10044b15f  jnz     short loc_10044B153
0x10044b161  mov     r10, qword ptr [rbp+230h+var_288]
0x10044b165  test    edx, edx
0x10044b167  mov     r9d, 1
0x10044b16d  cmovnz  r9d, edx; unsigned int *
0x10044b171  mov     edx, dword ptr [rbp+230h+var_290]
0x10044b174  lea     rcx, [r10+rdx*4]
0x10044b178  test    edx, edx
0x10044b17a  jz      short loc_10044B18E
0x10044b17c  nop     dword ptr [rax+00h]
0x10044b180  cmp     [rcx-4], edi
0x10044b183  lea     rcx, [rcx-4]
0x10044b187  jnz     short loc_10044B18E
0x10044b189  add     edx, 0FFFFFFFFh
0x10044b18c  jnz     short loc_10044B180
0x10044b18e  xorps   xmm0, xmm0
0x10044b191  test    edx, edx
0x10044b193  mov     eax, 1
0x10044b198  cmovnz  eax, edx
0x10044b19b  xor     ecx, ecx
0x10044b19d  mov     [rbp+230h+var_20], rcx
0x10044b1a4  lea     rcx, [rbp+230h+Source]; this
0x10044b1ab  mov     dword ptr [rsp+330h+var_308], eax; unsigned int *
0x10044b1af  movups  [rbp+230h+Source], xmm0
0x10044b1b6  lea     ebx, [rax+r9]
0x10044b1ba  mov     qword ptr [rsp+330h+var_310], r10; int
0x10044b1bf  mov     edx, ebx; unsigned int *
0x10044b1c1  movups  [rbp+230h+var_50], xmm0
0x10044b1c8  movups  [rbp+230h+var_40], xmm0
0x10044b1cf  movups  [rbp+230h+var_30], xmm0
0x10044b1d6  call    ?EaMultiply@RobustIntersections@@YAIPEAIHPEBIH1H@Z; RobustIntersections::EaMultiply(uint *,int,uint const *,int,uint const *,int)
0x10044b1db  mov     rcx, [rsp+330h+Destination]; Destination
0x10044b1e0  lea     r8, [rbp+230h+Source]; Source
0x10044b1e7  mov     edx, ebx
0x10044b1e9  shl     rdx, 2; DestinationSize
0x10044b1ed  mov     r9, rdx; SourceSize
0x10044b1f0  call    memcpy_s
0x10044b1f5  mov     eax, dword ptr [rsp+330h+var_300+4]
0x10044b1f9  imul    eax, dword ptr [rbp+230h+var_290+4]
0x10044b1fd  mov     edx, dword ptr [rsp+330h+var_2C8]
0x10044b201  mov     r8, [rsp+330h+var_2C0]; int
0x10044b206  mov     dword ptr [rsp+330h+var_300+4], eax
0x10044b20a  lea     rcx, [r8+rdx*4]
0x10044b20e  test    edx, edx
0x10044b210  jz      short loc_10044B220
0x10044b212  cmp     [rcx-4], edi
0x10044b215  lea     rcx, [rcx-4]
0x10044b219  jnz     short loc_10044B220
0x10044b21b  add     edx, 0FFFFFFFFh
0x10044b21e  jnz     short loc_10044B212
0x10044b220  mov     r10, qword ptr [rbp+230h+var_250]
0x10044b224  test    edx, edx
0x10044b226  mov     r9d, 1
0x10044b22c  cmovnz  r9d, edx; unsigned int *
0x10044b230  mov     edx, dword ptr [rbp+230h+var_258]
0x10044b233  lea     rcx, [r10+rdx*4]
0x10044b237  test    edx, edx
0x10044b239  jz      short loc_10044B24E
0x10044b23b  nop     dword ptr [rax+rax+00h]
0x10044b240  cmp     [rcx-4], edi
0x10044b243  lea     rcx, [rcx-4]
0x10044b247  jnz     short loc_10044B24E
0x10044b249  add     edx, 0FFFFFFFFh
0x10044b24c  jnz     short loc_10044B240
0x10044b24e  xorps   xmm0, xmm0
0x10044b251  test    edx, edx
0x10044b253  mov     eax, 1
0x10044b258  cmovnz  eax, edx
0x10044b25b  xor     ecx, ecx
0x10044b25d  mov     [rbp+230h+var_20], rcx
0x10044b264  lea     rcx, [rbp+230h+Source]; this
0x10044b26b  mov     dword ptr [rsp+330h+var_308], eax; unsigned int *
0x10044b26f  movups  [rbp+230h+Source], xmm0
0x10044b276  lea     ebx, [rax+r9]
0x10044b27a  mov     qword ptr [rsp+330h+var_310], r10; int
0x10044b27f  mov     edx, ebx; unsigned int *
0x10044b281  movups  [rbp+230h+var_50], xmm0
0x10044b288  movups  [rbp+230h+var_40], xmm0
0x10044b28f  movups  [rbp+230h+var_30], xmm0
0x10044b296  call    ?EaMultiply@RobustIntersections@@YAIPEAIHPEBIH1H@Z; RobustIntersections::EaMultiply(uint *,int,uint const *,int,uint const *,int)
0x10044b29b  mov     rcx, [rsp+330h+var_2C0]; Destination
0x10044b2a0  lea     r8, [rbp+230h+Source]; Source
0x10044b2a7  mov     edx, ebx
0x10044b2a9  shl     rdx, 2; DestinationSize
0x10044b2ad  mov     r9, rdx; SourceSize
0x10044b2b0  call    memcpy_s
0x10044b2b5  mov     eax, dword ptr [rsp+330h+var_2C8+4]
0x10044b2b9  imul    eax, dword ptr [rbp+230h+var_258+4]
0x10044b2bd  mov     dword ptr [rsp+330h+var_2C8+4], eax
0x10044b2c1  cmp     eax, dword ptr [rsp+330h+var_300+4]
0x10044b2c5  jle     short loc_10044B2D3
0x10044b2c7  mov     edi, 1
0x10044b2cc  neg     edi
0x10044b2ce  jmp     loc_10044B386
0x10044b2d3  jge     short loc_10044B2E1
0x10044b2d5  mov     edi, 0FFFFFFFFh
0x10044b2da  neg     edi
0x10044b2dc  jmp     loc_10044B386
0x10044b2e1  test    eax, eax
0x10044b2e3  jle     short loc_10044B306
0x10044b2e5  mov     r9d, dword ptr [rsp+330h+var_300]
0x10044b2ea  mov     r8, [rsp+330h+Destination]
0x10044b2ef  mov     edx, dword ptr [rsp+330h+var_2C8]
0x10044b2f3  mov     rcx, [rsp+330h+var_2C0]
0x10044b2f8  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044b2fd  mov     edi, eax
0x10044b2ff  neg     edi
0x10044b301  jmp     loc_10044B386
0x10044b306  jns     short loc_10044B322
0x10044b308  mov     r9d, dword ptr [rsp+330h+var_2C8]
0x10044b30d  mov     r8, [rsp+330h+var_2C0]
0x10044b312  mov     edx, dword ptr [rsp+330h+var_300]
0x10044b316  mov     rcx, [rsp+330h+Destination]
0x10044b31b  call    ?EaCompare@RobustIntersections@@YA?AW4COMPARISON@1@PEBIH0H@Z; RobustIntersections::EaCompare(uint const *,int,uint const *,int)
0x10044b320  mov     edi, eax
0x10044b322  neg     edi
0x10044b324  jmp     short loc_10044B386
0x10044b326  lea     rdx, [rbp+230h+var_290]
0x10044b32a  lea     rcx, [rsp+330h+var_300]
0x10044b32f  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b334  lea     rdx, [rbp+230h+var_258]
0x10044b338  mov     rbx, rax
0x10044b33b  lea     rcx, [rsp+330h+var_2C8]
0x10044b340  call    ?Multiply@?$CZ@$0IA@@RobustIntersections@@QEAAAEAV12@AEBV12@@Z; RobustIntersections::CZ<128>::Multiply(RobustIntersections::CZ<128> const &)
0x10044b345  mov     ecx, [rax+4]
0x10044b348  cmp     ecx, [rbx+4]
0x10044b34b  jle     short loc_10044B354
0x10044b34d  mov     edi, 1
0x10044b352  jmp     short loc_10044B386
0x10044b354  jge     short loc_10044B35D
0x10044b356  mov     edi, 0FFFFFFFFh
0x10044b35b  jmp     short loc_10044B386
0x10044b35d  test    ecx, ecx
0x10044b35f  jle     short loc_10044B370
0x10044b361  mov     r9d, [rbx]
0x10044b364  mov     r8, [rbx+8]
0x10044b368  mov     edx, [rax]
0x10044b36a  mov     rcx, [rax+8]
0x10044b36e  jmp     short loc_10044B37F
0x10044b370  jns     short loc_10044B386
  ... truncated ...
```
