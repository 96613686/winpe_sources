# BfeFilterComputeWeight

- ea: `0x18000f200`
- end: `0x18000f7f5`
- name: `BfeFilterComputeWeight`
- size: `1525`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x18000f1a8`
- `0x18000f200`
- `0x18000f800`
- `0x18000fad0`
- `0x180010240`
- `0x180010ad0`
- `0x180012b54`
- `0x180018b74`
- `0x18004e230`
- `0x1800542bc`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f3f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f687`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f3f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f687`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f7c5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f7e3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f7c5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000f7e3`

## string_xrefs

- `0x18000f483`: `BfeFilterComputeWeight`
- `0x18000f416`: `BfeWeightInfoCompute`

## pseudocode

```c
__int64 __fastcall BfeFilterComputeWeight(unsigned __int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 *v4; // r14
  int v5; // eax
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 **v8; // rdi
  unsigned __int8 v9; // bp
  unsigned __int64 *v10; // r13
  __int64 v11; // rbx
  unsigned __int64 v12; // r12
  unsigned __int64 v13; // r15
  __int64 v14; // r14
  unsigned __int64 v15; // rbp
  double v16; // xmm7_8
  __int64 v17; // rbx
  double v18; // xmm6_8
  __int64 j; // rdi
  unsigned __int64 v20; // rax
  double v21; // xmm0_8
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  __int64 v24; // rsi
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // r8
  __int64 *v29; // rax
  __int64 v30; // rbx
  __int64 result; // rax
  unsigned __int64 *v32; // r13
  __int64 v33; // rbx
  unsigned __int64 v34; // r12
  unsigned __int64 v35; // r15
  __int64 v36; // r14
  unsigned __int64 v37; // rbp
  double v38; // xmm7_8
  __int64 v39; // rbx
  double v40; // xmm6_8
  __int64 i; // rdi
  unsigned __int64 v42; // rax
  double v43; // xmm0_8
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rax
  __int64 v46; // rsi
  const void *v47; // rax
  __int64 v48; // rcx
  __int64 *v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned __int8 v52; // [rsp+30h] [rbp-F8h]
  __int64 v53; // [rsp+38h] [rbp-F0h] BYREF
  __int64 *v54; // [rsp+40h] [rbp-E8h]
  __int64 v55; // [rsp+48h] [rbp-E0h]
  __int64 **v56; // [rsp+50h] [rbp-D8h]
  char v57[16]; // [rsp+58h] [rbp-D0h] BYREF
  const char *v58; // [rsp+68h] [rbp-C0h]
  __int64 v59; // [rsp+70h] [rbp-B8h]
  __int64 *v60; // [rsp+78h] [rbp-B0h]
  __int64 v61; // [rsp+80h] [rbp-A8h]

  v3 = *(_QWORD *)(a1 + 16);
  v4 = (__int64 *)a1;
  v5 = *(_DWORD *)(v3 + 8);
  v6 = v3 + 8;
  v54 = (__int64 *)a1;
  v55 = v3 + 8;
  if ( !v5 )
  {
    v32 = *(unsigned __int64 **)(*(_QWORD *)(a1 + 8) + 8LL);
    if ( v32 )
    {
      v33 = 0;
      v34 = 0;
      v53 = 0;
      if ( *v32 )
      {
        a2 = 1;
        do
        {
          v35 = v32[1];
          v36 = 32 * v34;
          v37 = 0;
          v38 = 0.0;
          if ( *(_QWORD *)(32 * v34 + v35 + 16) )
          {
            do
            {
              v39 = 0;
              v40 = 0.0;
              for ( i = *(_QWORD *)(v36 + v35 + 24) + 32 * v37;
                    (unsigned int)v39 < *(_DWORD *)(v3 + 28);
                    v39 = (unsigned int)(v39 + 1) )
              {
                if ( *(_WORD *)(*(_QWORD *)(v3 + 32) + 24 * v39) == *(_WORD *)i )
                  v40 = v40 + BfeWeightFieldComputeFromCondition(i);
              }
              ++v37;
              v38 = v38 + fmin(*(double *)(i + 8), v40);
            }
            while ( v37 < *(_QWORD *)(v36 + v35 + 16) );
            v33 = v53;
            a2 = 1;
          }
          v42 = 0;
          v43 = v38 + 0.5;
          if ( v38 + 0.5 >= 9.223372036854776e18 )
          {
            v43 = v43 - 9.223372036854776e18;
            if ( v43 < 9.223372036854776e18 )
              v42 = 0x8000000000000000uLL;
          }
          v44 = v42 + (unsigned int)(int)v43;
          if ( !v44 )
            v44 = v38 > 0.0;
          v45 = *(_QWORD *)(v36 + v35);
          if ( v44 <= v45 )
            v45 = v44;
          ++v34;
          v33 |= v45 << *(_QWORD *)(v36 + v35 + 8);
          a1 = 0x8000000000000000uLL;
          v53 = v33;
        }
        while ( v34 < *v32 );
        v4 = v54;
        v6 = v55;
      }
      v46 = v33;
    }
    else
    {
      v46 = 0x7FFFFFFFFFFFFFFLL;
    }
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(a1, a2, a3) )
    {
      v27 = WfpMemAlloc25B(8u);
    }
    else
    {
      v47 = HeapAlloc(gWfpHeap, 0, 8u);
      *(_QWORD *)(v6 + 8) = v47;
      if ( v47 )
      {
        v27 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v47));
      }
      else
      {
        v51 = WfpReportSysErrorAsNtStatus(v48, "HeapAlloc", 3221225495LL);
        v27 = v51;
        if ( v51 )
          WfpReportError(v51, "WfpMemAlloc");
      }
    }
    if ( v27 )
      goto LABEL_28;
    v49 = *(__int64 **)(v6 + 8);
    *(_DWORD *)v6 = 4;
    *v49 = v46;
LABEL_30:
    v30 = *v4;
    BfeDestroyInner_FWP_VALUE0(*v4 + 184);
    *(_OWORD *)(v30 + 184) = 0;
    result = BfeFwpConditionValueCopyInner(v6, *v4 + 184);
    v27 = result;
    if ( !result )
      return result;
    goto LABEL_31;
  }
  if ( v5 != 1 )
    goto LABEL_30;
  v7 = *(_QWORD *)(a1 + 8);
  v8 = (__int64 **)(v3 + 16);
  v9 = *(_BYTE *)(v3 + 16);
  v56 = (__int64 **)(v3 + 16);
  v52 = v9;
  v10 = *(unsigned __int64 **)(v7 + 8);
  if ( v10 )
  {
    v11 = 0;
    v12 = 0;
    v53 = 0;
    if ( *v10 )
    {
      a2 = 1;
      do
      {
        v13 = v10[1];
        v14 = 32 * v12;
        v15 = 0;
        v16 = 0.0;
        if ( *(_QWORD *)(32 * v12 + v13 + 16) )
        {
          do
          {
            v17 = 0;
            v18 = 0.0;
            for ( j = *(_QWORD *)(v14 + v13 + 24) + 32 * v15;
                  (unsigned int)v17 < *(_DWORD *)(v3 + 28);
                  v17 = (unsigned int)(v17 + 1) )
            {
              if ( *(_WORD *)(*(_QWORD *)(v3 + 32) + 24 * v17) == *(_WORD *)j )
                v18 = v18 + BfeWeightFieldComputeFromCondition(j);
            }
            ++v15;
            v16 = v16 + fmin(*(double *)(j + 8), v18);
          }
          while ( v15 < *(_QWORD *)(v14 + v13 + 16) );
          v11 = v53;
          a2 = 1;
        }
        v20 = 0;
        v21 = v16 + 0.5;
        if ( v16 + 0.5 >= 9.223372036854776e18 )
        {
          v21 = v21 - 9.223372036854776e18;
          if ( v21 < 9.223372036854776e18 )
            v20 = 0x8000000000000000uLL;
        }
        v22 = v20 + (unsigned int)(int)v21;
        if ( !v22 )
          v22 = v16 > 0.0;
        v23 = *(_QWORD *)(v14 + v13);
        if ( v22 <= v23 )
          v23 = v22;
        ++v12;
        v11 |= v23 << *(_QWORD *)(v14 + v13 + 8);
        a1 = 0x8000000000000000uLL;
        v53 = v11;
      }
      while ( v12 < *v10 );
      v8 = v56;
      v9 = v52;
      v4 = v54;
      v6 = v55;
    }
    v24 = v11;
  }
  else
  {
    v24 = 0x7FFFFFFFFFFFFFFLL;
  }
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(a1, a2, a3) )
  {
    v27 = WfpMemAlloc25B(8u);
  }
  else
  {
    v25 = (__int64 *)HeapAlloc(gWfpHeap, 0, 8u);
    *v8 = v25;
    if ( v25 )
    {
      v27 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v25));
    }
    else
    {
      v50 = WfpReportSysErrorAsNtStatus(v26, "HeapAlloc", 3221225495LL);
      v27 = v50;
      if ( v50 )
        WfpReportError(v50, "WfpMemAlloc");
    }
  }
  if ( !v27 )
  {
    v29 = *v8;
    *(_DWORD *)v6 = 4;
    *v29 = v24;
    **v8 |= (unsigned __int64)v9 << 60;
    goto LABEL_30;
  }
LABEL_28:
  WfpReportError(v27, "BfeWeightInfoCompute");
LABEL_31:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v28, 0, (__int64)"BfeFilterComputeWeight", v27);
  }
  if ( MEMORY[0x1800EF078] )
  {
    if ( (qword_1800F2668[337] & 0x10000000000LL) != 0 )
    {
      LODWORD(v53) = v27;
      v60 = &v53;
      v58 = "BfeFilterComputeWeight";
      v59 = 23;
      v61 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        v28,
        3,
        (__int64)v57);
    }
  }
  return v27;
}

```

## disassembly

```asm
0x18000f200  mov     rax, rsp
0x18000f203  push    rbx
0x18000f204  push    rbp
0x18000f205  push    rsi
0x18000f206  push    rdi
0x18000f207  push    r12
0x18000f209  push    r13
0x18000f20b  push    r14
0x18000f20d  push    r15
0x18000f20f  sub     rsp, 0E8h
0x18000f216  movaps  xmmword ptr [rax-58h], xmm6
0x18000f21a  movaps  xmmword ptr [rax-68h], xmm7
0x18000f21e  movaps  xmmword ptr [rax-78h], xmm8
0x18000f223  movaps  xmmword ptr [rax-88h], xmm9
0x18000f22b  movaps  xmmword ptr [rax-98h], xmm10
0x18000f233  mov     rax, cs:__security_cookie
0x18000f23a  xor     rax, rsp
0x18000f23d  mov     [rsp+128h+var_A0], rax
0x18000f245  mov     rsi, [rcx+10h]
0x18000f249  mov     r14, rcx
0x18000f24c  mov     eax, [rsi+8]
0x18000f24f  lea     r15, [rsi+8]
0x18000f253  mov     [rsp+128h+var_E8], rcx
0x18000f258  mov     [rsp+128h+var_E0], r15
0x18000f25d  test    eax, eax
0x18000f25f  jz      loc_18000F51B
0x18000f265  cmp     eax, 1
0x18000f268  jnz     loc_18000F442
0x18000f26e  mov     rax, [rcx+8]
0x18000f272  lea     rdi, [r15+8]
0x18000f276  movzx   ebp, byte ptr [rdi]
0x18000f279  mov     [rsp+128h+var_D8], rdi
0x18000f27e  mov     [rsp+128h+var_F8], bpl
0x18000f283  mov     r13, [rax+8]
0x18000f287  test    r13, r13
0x18000f28a  jz      loc_18000F737
0x18000f290  xor     ebx, ebx
0x18000f292  xor     r12d, r12d
0x18000f295  mov     [rsp+128h+var_F0], rbx
0x18000f29a  cmp     [r13+0], rbx
0x18000f29e  jbe     loc_18000F3D2
0x18000f2a4  movsd   xmm10, cs:__real@3fe0000000000000
0x18000f2ad  mov     rcx, 8000000000000000h
0x18000f2b7  movsd   xmm9, cs:__real@43e0000000000000
0x18000f2c0  mov     edx, 1
0x18000f2c5  xorps   xmm8, xmm8
0x18000f2c9  nop     dword ptr [rax+00000000h]
0x18000f2d0  mov     r15, [r13+8]
0x18000f2d4  mov     r14, r12
0x18000f2d7  shl     r14, 5
0x18000f2db  xor     ebp, ebp
0x18000f2dd  movaps  xmm7, xmm8
0x18000f2e1  cmp     [r14+r15+10h], rbp
0x18000f2e6  jbe     short loc_18000F359
0x18000f2e8  nop     dword ptr [rax+rax+00000000h]
0x18000f2f0  mov     rdi, rbp
0x18000f2f3  xor     ebx, ebx
0x18000f2f5  shl     rdi, 5
0x18000f2f9  movaps  xmm6, xmm8
0x18000f2fd  add     rdi, [r14+r15+18h]
0x18000f302  cmp     [rsi+1Ch], ebx
0x18000f305  jbe     short loc_18000F32E
0x18000f307  mov     rax, [rsi+20h]
0x18000f30b  lea     rcx, [rbx+rbx*2]
0x18000f30f  lea     rdx, [rax+rcx*8]
0x18000f313  movzx   eax, word ptr [rdi]
0x18000f316  cmp     [rdx], ax
0x18000f319  jnz     short loc_18000F327
0x18000f31b  mov     rcx, rdi
0x18000f31e  call    BfeWeightFieldComputeFromCondition
0x18000f323  addsd   xmm6, xmm0
0x18000f327  inc     ebx
0x18000f329  cmp     ebx, [rsi+1Ch]
0x18000f32c  jb      short loc_18000F307
0x18000f32e  movsd   xmm0, qword ptr [rdi+8]
0x18000f333  inc     rbp
0x18000f336  minsd   xmm0, xmm6
0x18000f33a  addsd   xmm7, xmm0
0x18000f33e  cmp     rbp, [r14+r15+10h]
0x18000f343  jb      short loc_18000F2F0
0x18000f345  mov     rbx, [rsp+128h+var_F0]
0x18000f34a  mov     rcx, 8000000000000000h
0x18000f354  mov     edx, 1
0x18000f359  movaps  xmm0, xmm7
0x18000f35c  xor     eax, eax
0x18000f35e  addsd   xmm0, xmm10
0x18000f363  comisd  xmm0, xmm9
0x18000f368  jb      short loc_18000F379
0x18000f36a  subsd   xmm0, xmm9
0x18000f36f  comisd  xmm0, xmm9
0x18000f374  jnb     short loc_18000F379
0x18000f376  mov     rax, rcx
0x18000f379  cvttsd2si rcx, xmm0
0x18000f37e  add     rcx, rax
0x18000f381  jnz     short loc_18000F38C
0x18000f383  comisd  xmm7, xmm8
0x18000f388  cmova   rcx, rdx
0x18000f38c  mov     rax, [r14+r15]
0x18000f390  cmp     rcx, rax
0x18000f393  cmovbe  rax, rcx
0x18000f397  mov     rcx, [r14+r15+8]
0x18000f39c  shl     rax, cl
0x18000f39f  inc     r12
0x18000f3a2  or      rbx, rax
0x18000f3a5  mov     rcx, 8000000000000000h
0x18000f3af  mov     [rsp+128h+var_F0], rbx
0x18000f3b4  cmp     r12, [r13+0]
0x18000f3b8  jb      loc_18000F2D0
0x18000f3be  mov     rdi, [rsp+128h+var_D8]
0x18000f3c3  movzx   ebp, [rsp+128h+var_F8]
0x18000f3c8  mov     r14, [rsp+128h+var_E8]
0x18000f3cd  mov     r15, [rsp+128h+var_E0]
0x18000f3d2  mov     rsi, rbx
0x18000f3d5  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000f3da  xor     edx, edx; dwFlags
0x18000f3dc  test    eax, eax
0x18000f3de  jnz     loc_18000F506
0x18000f3e4  mov     rcx, cs:gWfpHeap; hHeap
0x18000f3eb  mov     r8d, 8; dwBytes
0x18000f3f1  call    cs:__imp_HeapAlloc
0x18000f3f7  mov     [rdi], rax
0x18000f3fa  test    rax, rax
0x18000f3fd  jz      loc_18000F755
0x18000f403  xor     ebx, ebx
0x18000f405  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000f40b  jnz     loc_18000F7D7
0x18000f411  test    rbx, rbx
0x18000f414  jz      short loc_18000F427
0x18000f416  lea     rdx, aBfeweightinfoc; "BfeWeightInfoCompute"
0x18000f41d  mov     rcx, rbx
0x18000f420  call    WfpReportError
0x18000f425  jmp     short loc_18000F475
0x18000f427  mov     rax, [rdi]
0x18000f42a  mov     dword ptr [r15], 4
0x18000f431  mov     [rax], rsi
0x18000f434  mov     rcx, [rdi]
0x18000f437  movzx   eax, bpl
0x18000f43b  shl     rax, 3Ch
0x18000f43f  or      [rcx], rax
0x18000f442  mov     rbx, [r14]
0x18000f445  lea     rcx, [rbx+0B8h]
0x18000f44c  call    BfeDestroyInner_FWP_VALUE0
0x18000f451  xorps   xmm0, xmm0
0x18000f454  mov     rcx, r15
0x18000f457  movups  xmmword ptr [rbx+0B8h], xmm0
0x18000f45e  mov     rdx, [r14]
0x18000f461  add     rdx, 0B8h
0x18000f468  call    BfeFwpConditionValueCopyInner
0x18000f46d  mov     rbx, rax
0x18000f470  test    rax, rax
0x18000f473  jz      short loc_18000F4C5
0x18000f475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f47c  lea     rax, WPP_GLOBAL_Control
0x18000f483  lea     rdi, aBfefiltercompu; "BfeFilterComputeWeight"
0x18000f48a  cmp     rcx, rax
0x18000f48d  jz      short loc_18000F4B5
0x18000f48f  cmp     byte ptr [rcx+19h], 2
0x18000f493  jb      short loc_18000F4B5
0x18000f495  test    byte ptr [rcx+1Ch], 1
0x18000f499  jz      short loc_18000F4B5
0x18000f49b  mov     rcx, [rcx+10h]
0x18000f49f  mov     edx, 1Ah
0x18000f4a4  mov     [rsp+128h+var_100], ebx
0x18000f4a8  xor     r9d, r9d
0x18000f4ab  mov     [rsp+128h+var_108], rdi
0x18000f4b0  call    WPP_SF_Ssd
0x18000f4b5  cmp     dword ptr cs:1800EF078h, 0
0x18000f4bc  jnz     loc_18000F6C4
0x18000f4c2  mov     rax, rbx
0x18000f4c5  mov     rcx, [rsp+128h+var_A0]
0x18000f4cd  xor     rcx, rsp; StackCookie
0x18000f4d0  call    __security_check_cookie
0x18000f4d5  lea     r11, [rsp+128h+var_40]
0x18000f4dd  movaps  xmm6, xmmword ptr [r11-18h]
0x18000f4e2  movaps  xmm7, xmmword ptr [r11-28h]
0x18000f4e7  movaps  xmm8, xmmword ptr [r11-38h]
0x18000f4ec  movaps  xmm9, xmmword ptr [r11-48h]
0x18000f4f1  movaps  xmm10, xmmword ptr [r11-58h]
0x18000f4f6  mov     rsp, r11
0x18000f4f9  pop     r15
0x18000f4fb  pop     r14
0x18000f4fd  pop     r13
0x18000f4ff  pop     r12
0x18000f501  pop     rdi
0x18000f502  pop     rsi
0x18000f503  pop     rbp
0x18000f504  pop     rbx
0x18000f505  retn
0x18000f506  mov     r8, rdi
0x18000f509  mov     ecx, 8; dwBytes
0x18000f50e  call    WfpMemAlloc25B
0x18000f513  mov     rbx, rax
0x18000f516  jmp     loc_18000F411
0x18000f51b  mov     rax, [rcx+8]
0x18000f51f  mov     r13, [rax+8]
0x18000f523  test    r13, r13
0x18000f526  jz      loc_18000F746
0x18000f52c  xor     ebx, ebx
0x18000f52e  xor     r12d, r12d
0x18000f531  mov     [rsp+128h+var_F0], rbx
0x18000f536  cmp     [r13+0], rbx
0x18000f53a  jbe     loc_18000F668
0x18000f540  movsd   xmm10, cs:__real@3fe0000000000000
0x18000f549  mov     rcx, 8000000000000000h
0x18000f553  movsd   xmm9, cs:__real@43e0000000000000
0x18000f55c  mov     edx, 1
0x18000f561  xorps   xmm8, xmm8
0x18000f565  nop     word ptr [rax+rax+00000000h]
0x18000f570  mov     r15, [r13+8]
0x18000f574  mov     r14, r12
0x18000f577  shl     r14, 5
0x18000f57b  xor     ebp, ebp
0x18000f57d  movaps  xmm7, xmm8
0x18000f581  cmp     [r14+r15+10h], rbp
0x18000f586  jbe     short loc_18000F5F9
0x18000f588  nop     dword ptr [rax+rax+00000000h]
0x18000f590  mov     rdi, rbp
0x18000f593  xor     ebx, ebx
0x18000f595  shl     rdi, 5
0x18000f599  movaps  xmm6, xmm8
0x18000f59d  add     rdi, [r14+r15+18h]
0x18000f5a2  cmp     [rsi+1Ch], ebx
0x18000f5a5  jbe     short loc_18000F5CE
0x18000f5a7  mov     rax, [rsi+20h]
0x18000f5ab  lea     rcx, [rbx+rbx*2]
0x18000f5af  lea     rdx, [rax+rcx*8]
0x18000f5b3  movzx   eax, word ptr [rdi]
0x18000f5b6  cmp     [rdx], ax
0x18000f5b9  jnz     short loc_18000F5C7
0x18000f5bb  mov     rcx, rdi
0x18000f5be  call    BfeWeightFieldComputeFromCondition
0x18000f5c3  addsd   xmm6, xmm0
0x18000f5c7  inc     ebx
0x18000f5c9  cmp     ebx, [rsi+1Ch]
0x18000f5cc  jb      short loc_18000F5A7
0x18000f5ce  movsd   xmm0, qword ptr [rdi+8]
0x18000f5d3  inc     rbp
0x18000f5d6  minsd   xmm0, xmm6
0x18000f5da  addsd   xmm7, xmm0
0x18000f5de  cmp     rbp, [r14+r15+10h]
0x18000f5e3  jb      short loc_18000F590
0x18000f5e5  mov     rbx, [rsp+128h+var_F0]
0x18000f5ea  mov     rcx, 8000000000000000h
0x18000f5f4  mov     edx, 1
0x18000f5f9  movaps  xmm0, xmm7
0x18000f5fc  xor     eax, eax
0x18000f5fe  addsd   xmm0, xmm10
0x18000f603  comisd  xmm0, xmm9
0x18000f608  jb      short loc_18000F619
0x18000f60a  subsd   xmm0, xmm9
0x18000f60f  comisd  xmm0, xmm9
0x18000f614  jnb     short loc_18000F619
0x18000f616  mov     rax, rcx
0x18000f619  cvttsd2si rcx, xmm0
0x18000f61e  add     rcx, rax
0x18000f621  jnz     short loc_18000F62C
0x18000f623  comisd  xmm7, xmm8
0x18000f628  cmova   rcx, rdx
0x18000f62c  mov     rax, [r14+r15]
0x18000f630  cmp     rcx, rax
0x18000f633  cmovbe  rax, rcx
0x18000f637  mov     rcx, [r14+r15+8]
0x18000f63c  shl     rax, cl
0x18000f63f  inc     r12
0x18000f642  or      rbx, rax
0x18000f645  mov     rcx, 8000000000000000h
0x18000f64f  mov     [rsp+128h+var_F0], rbx
0x18000f654  cmp     r12, [r13+0]
0x18000f658  jb      loc_18000F570
0x18000f65e  mov     r14, [rsp+128h+var_E8]
0x18000f663  mov     r15, [rsp+128h+var_E0]
0x18000f668  mov     rsi, rbx
0x18000f66b  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000f670  xor     edx, edx; dwFlags
0x18000f672  test    eax, eax
0x18000f674  jnz     loc_18000F721
0x18000f67a  mov     rcx, cs:gWfpHeap; hHeap
0x18000f681  mov     r8d, 8; dwBytes
0x18000f687  call    cs:__imp_HeapAlloc
0x18000f68d  mov     [r15+8], rax
0x18000f691  test    rax, rax
0x18000f694  jz      loc_18000F787
0x18000f69a  xor     ebx, ebx
0x18000f69c  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000f6a2  jnz     loc_18000F7B9
0x18000f6a8  test    rbx, rbx
0x18000f6ab  jnz     loc_18000F416
0x18000f6b1  mov     rax, [r15+8]
0x18000f6b5  mov     dword ptr [r15], 4
0x18000f6bc  mov     [rax], rsi
0x18000f6bf  jmp     loc_18000F442
0x18000f6c4  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18000f6cb  jz      loc_18000F4C2
0x18000f6d1  lea     rax, [rsp+128h+var_F0]
0x18000f6d6  mov     dword ptr [rsp+128h+var_F0], ebx
0x18000f6da  mov     [rsp+128h+var_B0], rax
0x18000f6df  lea     rdx, WFP_USERMODE_ERROR
0x18000f6e6  lea     rax, [rsp+128h+var_D0]
0x18000f6eb  mov     [rsp+128h+var_C0], rdi
0x18000f6f0  mov     r9d, 3
  ... truncated ...
```
