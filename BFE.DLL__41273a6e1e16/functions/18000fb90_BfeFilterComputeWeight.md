# BfeFilterComputeWeight

- ea: `0x18000fb90`
- end: `0x180010197`
- name: `BfeFilterComputeWeight`
- size: `1543`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180006ed0`

## callees

- `0x18000fb34`
- `0x18000fb90`
- `0x1800101a0`
- `0x180010480`
- `0x180010c30`
- `0x180011510`
- `0x1800135ac`
- `0x1800197d0`
- `0x18004fb50`
- `0x1800560f8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010017`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fd81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010017`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001015b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001017f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001015b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001017f`

## string_xrefs

- `0x18000fe19`: `BfeFilterComputeWeight`
- `0x18000fdac`: `BfeWeightInfoCompute`

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
  if ( gWfpLogUserModeErrors )
  {
    if ( (byte_1800F6115 & 1) != 0 )
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
0x18000fb90  mov     rax, rsp
0x18000fb93  push    rbx
0x18000fb94  push    rbp
0x18000fb95  push    rsi
0x18000fb96  push    rdi
0x18000fb97  push    r12
0x18000fb99  push    r13
0x18000fb9b  push    r14
0x18000fb9d  push    r15
0x18000fb9f  sub     rsp, 0E8h
0x18000fba6  movaps  xmmword ptr [rax-58h], xmm6
0x18000fbaa  movaps  xmmword ptr [rax-68h], xmm7
0x18000fbae  movaps  xmmword ptr [rax-78h], xmm8
0x18000fbb3  movaps  xmmword ptr [rax-88h], xmm9
0x18000fbbb  movaps  xmmword ptr [rax-98h], xmm10
0x18000fbc3  mov     rax, cs:__security_cookie
0x18000fbca  xor     rax, rsp
0x18000fbcd  mov     [rsp+128h+var_A0], rax
0x18000fbd5  mov     rsi, [rcx+10h]
0x18000fbd9  mov     r14, rcx
0x18000fbdc  mov     eax, [rsi+8]
0x18000fbdf  lea     r15, [rsi+8]
0x18000fbe3  mov     [rsp+128h+var_E8], rcx
0x18000fbe8  mov     [rsp+128h+var_E0], r15
0x18000fbed  test    eax, eax
0x18000fbef  jz      loc_18000FEB2
0x18000fbf5  cmp     eax, 1
0x18000fbf8  jnz     loc_18000FDD8
0x18000fbfe  mov     rax, [rcx+8]
0x18000fc02  lea     rdi, [r15+8]
0x18000fc06  movzx   ebp, byte ptr [rdi]
0x18000fc09  mov     [rsp+128h+var_D8], rdi
0x18000fc0e  mov     [rsp+128h+var_F8], bpl
0x18000fc13  mov     r13, [rax+8]
0x18000fc17  test    r13, r13
0x18000fc1a  jz      loc_1800100CD
0x18000fc20  xor     ebx, ebx
0x18000fc22  xor     r12d, r12d
0x18000fc25  mov     [rsp+128h+var_F0], rbx
0x18000fc2a  cmp     [r13+0], rbx
0x18000fc2e  jbe     loc_18000FD62
0x18000fc34  movsd   xmm10, cs:__real@3fe0000000000000
0x18000fc3d  mov     rcx, 8000000000000000h
0x18000fc47  movsd   xmm9, cs:__real@43e0000000000000
0x18000fc50  mov     edx, 1
0x18000fc55  xorps   xmm8, xmm8
0x18000fc59  nop     dword ptr [rax+00000000h]
0x18000fc60  mov     r15, [r13+8]
0x18000fc64  mov     r14, r12
0x18000fc67  shl     r14, 5
0x18000fc6b  xor     ebp, ebp
0x18000fc6d  movaps  xmm7, xmm8
0x18000fc71  cmp     [r14+r15+10h], rbp
0x18000fc76  jbe     short loc_18000FCE9
0x18000fc78  nop     dword ptr [rax+rax+00000000h]
0x18000fc80  mov     rdi, rbp
0x18000fc83  xor     ebx, ebx
0x18000fc85  shl     rdi, 5
0x18000fc89  movaps  xmm6, xmm8
0x18000fc8d  add     rdi, [r14+r15+18h]
0x18000fc92  cmp     [rsi+1Ch], ebx
0x18000fc95  jbe     short loc_18000FCBE
0x18000fc97  mov     rax, [rsi+20h]
0x18000fc9b  lea     rcx, [rbx+rbx*2]
0x18000fc9f  lea     rdx, [rax+rcx*8]
0x18000fca3  movzx   eax, word ptr [rdi]
0x18000fca6  cmp     [rdx], ax
0x18000fca9  jnz     short loc_18000FCB7
0x18000fcab  mov     rcx, rdi
0x18000fcae  call    BfeWeightFieldComputeFromCondition
0x18000fcb3  addsd   xmm6, xmm0
0x18000fcb7  inc     ebx
0x18000fcb9  cmp     ebx, [rsi+1Ch]
0x18000fcbc  jb      short loc_18000FC97
0x18000fcbe  movsd   xmm0, qword ptr [rdi+8]
0x18000fcc3  inc     rbp
0x18000fcc6  minsd   xmm0, xmm6
0x18000fcca  addsd   xmm7, xmm0
0x18000fcce  cmp     rbp, [r14+r15+10h]
0x18000fcd3  jb      short loc_18000FC80
0x18000fcd5  mov     rbx, [rsp+128h+var_F0]
0x18000fcda  mov     rcx, 8000000000000000h
0x18000fce4  mov     edx, 1
0x18000fce9  movaps  xmm0, xmm7
0x18000fcec  xor     eax, eax
0x18000fcee  addsd   xmm0, xmm10
0x18000fcf3  comisd  xmm0, xmm9
0x18000fcf8  jb      short loc_18000FD09
0x18000fcfa  subsd   xmm0, xmm9
0x18000fcff  comisd  xmm0, xmm9
0x18000fd04  jnb     short loc_18000FD09
0x18000fd06  mov     rax, rcx
0x18000fd09  cvttsd2si rcx, xmm0
0x18000fd0e  add     rcx, rax
0x18000fd11  jnz     short loc_18000FD1C
0x18000fd13  comisd  xmm7, xmm8
0x18000fd18  cmova   rcx, rdx
0x18000fd1c  mov     rax, [r14+r15]
0x18000fd20  cmp     rcx, rax
0x18000fd23  cmovbe  rax, rcx
0x18000fd27  mov     rcx, [r14+r15+8]
0x18000fd2c  shl     rax, cl
0x18000fd2f  inc     r12
0x18000fd32  or      rbx, rax
0x18000fd35  mov     rcx, 8000000000000000h
0x18000fd3f  mov     [rsp+128h+var_F0], rbx
0x18000fd44  cmp     r12, [r13+0]
0x18000fd48  jb      loc_18000FC60
0x18000fd4e  mov     rdi, [rsp+128h+var_D8]
0x18000fd53  movzx   ebp, [rsp+128h+var_F8]
0x18000fd58  mov     r14, [rsp+128h+var_E8]
0x18000fd5d  mov     r15, [rsp+128h+var_E0]
0x18000fd62  mov     rsi, rbx
0x18000fd65  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000fd6a  xor     edx, edx; dwFlags
0x18000fd6c  test    eax, eax
0x18000fd6e  jnz     loc_18000FE9D
0x18000fd74  mov     rcx, cs:gWfpHeap; hHeap
0x18000fd7b  mov     r8d, 8; dwBytes
0x18000fd81  call    cs:__imp_HeapAlloc
0x18000fd88  nop     dword ptr [rax+rax+00h]
0x18000fd8d  mov     [rdi], rax
0x18000fd90  test    rax, rax
0x18000fd93  jz      loc_1800100EB
0x18000fd99  xor     ebx, ebx
0x18000fd9b  cmp     cs:gWfpTrackHeapBytes, ebx
0x18000fda1  jnz     loc_180010173
0x18000fda7  test    rbx, rbx
0x18000fdaa  jz      short loc_18000FDBD
0x18000fdac  lea     rdx, aBfeweightinfoc; "BfeWeightInfoCompute"
0x18000fdb3  mov     rcx, rbx
0x18000fdb6  call    WfpReportError
0x18000fdbb  jmp     short loc_18000FE0B
0x18000fdbd  mov     rax, [rdi]
0x18000fdc0  mov     dword ptr [r15], 4
0x18000fdc7  mov     [rax], rsi
0x18000fdca  mov     rcx, [rdi]
0x18000fdcd  movzx   eax, bpl
0x18000fdd1  shl     rax, 3Ch
0x18000fdd5  or      [rcx], rax
0x18000fdd8  mov     rbx, [r14]
0x18000fddb  lea     rcx, [rbx+0B8h]
0x18000fde2  call    BfeDestroyInner_FWP_VALUE0
0x18000fde7  xorps   xmm0, xmm0
0x18000fdea  mov     rcx, r15
0x18000fded  movups  xmmword ptr [rbx+0B8h], xmm0
0x18000fdf4  mov     rdx, [r14]
0x18000fdf7  add     rdx, 0B8h
0x18000fdfe  call    BfeFwpConditionValueCopyInner
0x18000fe03  mov     rbx, rax
0x18000fe06  test    rax, rax
0x18000fe09  jz      short loc_18000FE5B
0x18000fe0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe12  lea     rax, WPP_GLOBAL_Control
0x18000fe19  lea     rdi, aBfefiltercompu; "BfeFilterComputeWeight"
0x18000fe20  cmp     rcx, rax
0x18000fe23  jz      short loc_18000FE4B
0x18000fe25  cmp     byte ptr [rcx+19h], 2
0x18000fe29  jb      short loc_18000FE4B
0x18000fe2b  test    byte ptr [rcx+1Ch], 1
0x18000fe2f  jz      short loc_18000FE4B
0x18000fe31  mov     rcx, [rcx+10h]
0x18000fe35  mov     edx, 1Ah
0x18000fe3a  mov     [rsp+128h+var_100], ebx
0x18000fe3e  xor     r9d, r9d
0x18000fe41  mov     [rsp+128h+var_108], rdi
0x18000fe46  call    WPP_SF_Ssd
0x18000fe4b  cmp     cs:gWfpLogUserModeErrors, 0
0x18000fe52  jnz     loc_18001005A
0x18000fe58  mov     rax, rbx
0x18000fe5b  mov     rcx, [rsp+128h+var_A0]
0x18000fe63  xor     rcx, rsp; StackCookie
0x18000fe66  call    __security_check_cookie
0x18000fe6b  lea     r11, [rsp+128h+var_40]
0x18000fe73  movaps  xmm6, xmmword ptr [r11-18h]
0x18000fe78  movaps  xmm7, xmmword ptr [r11-28h]
0x18000fe7d  movaps  xmm8, xmmword ptr [r11-38h]
0x18000fe82  movaps  xmm9, xmmword ptr [r11-48h]
0x18000fe87  movaps  xmm10, xmmword ptr [r11-58h]
0x18000fe8c  mov     rsp, r11
0x18000fe8f  pop     r15
0x18000fe91  pop     r14
0x18000fe93  pop     r13
0x18000fe95  pop     r12
0x18000fe97  pop     rdi
0x18000fe98  pop     rsi
0x18000fe99  pop     rbp
0x18000fe9a  pop     rbx
0x18000fe9b  retn
0x18000fe9d  mov     r8, rdi
0x18000fea0  mov     ecx, 8; dwBytes
0x18000fea5  call    WfpMemAlloc25B
0x18000feaa  mov     rbx, rax
0x18000fead  jmp     loc_18000FDA7
0x18000feb2  mov     rax, [rcx+8]
0x18000feb6  mov     r13, [rax+8]
0x18000feba  test    r13, r13
0x18000febd  jz      loc_1800100DC
0x18000fec3  xor     ebx, ebx
0x18000fec5  xor     r12d, r12d
0x18000fec8  mov     [rsp+128h+var_F0], rbx
0x18000fecd  cmp     [r13+0], rbx
0x18000fed1  jbe     loc_18000FFF8
0x18000fed7  movsd   xmm10, cs:__real@3fe0000000000000
0x18000fee0  mov     rcx, 8000000000000000h
0x18000feea  movsd   xmm9, cs:__real@43e0000000000000
0x18000fef3  mov     edx, 1
0x18000fef8  xorps   xmm8, xmm8
0x18000fefc  nop     dword ptr [rax+00h]
0x18000ff00  mov     r15, [r13+8]
0x18000ff04  mov     r14, r12
0x18000ff07  shl     r14, 5
0x18000ff0b  xor     ebp, ebp
0x18000ff0d  movaps  xmm7, xmm8
0x18000ff11  cmp     [r14+r15+10h], rbp
0x18000ff16  jbe     short loc_18000FF89
0x18000ff18  nop     dword ptr [rax+rax+00000000h]
0x18000ff20  mov     rdi, rbp
0x18000ff23  xor     ebx, ebx
0x18000ff25  shl     rdi, 5
0x18000ff29  movaps  xmm6, xmm8
0x18000ff2d  add     rdi, [r14+r15+18h]
0x18000ff32  cmp     [rsi+1Ch], ebx
0x18000ff35  jbe     short loc_18000FF5E
0x18000ff37  mov     rax, [rsi+20h]
0x18000ff3b  lea     rcx, [rbx+rbx*2]
0x18000ff3f  lea     rdx, [rax+rcx*8]
0x18000ff43  movzx   eax, word ptr [rdi]
0x18000ff46  cmp     [rdx], ax
0x18000ff49  jnz     short loc_18000FF57
0x18000ff4b  mov     rcx, rdi
0x18000ff4e  call    BfeWeightFieldComputeFromCondition
0x18000ff53  addsd   xmm6, xmm0
0x18000ff57  inc     ebx
0x18000ff59  cmp     ebx, [rsi+1Ch]
0x18000ff5c  jb      short loc_18000FF37
0x18000ff5e  movsd   xmm0, qword ptr [rdi+8]
0x18000ff63  inc     rbp
0x18000ff66  minsd   xmm0, xmm6
0x18000ff6a  addsd   xmm7, xmm0
0x18000ff6e  cmp     rbp, [r14+r15+10h]
0x18000ff73  jb      short loc_18000FF20
0x18000ff75  mov     rbx, [rsp+128h+var_F0]
0x18000ff7a  mov     rcx, 8000000000000000h
0x18000ff84  mov     edx, 1
0x18000ff89  movaps  xmm0, xmm7
0x18000ff8c  xor     eax, eax
0x18000ff8e  addsd   xmm0, xmm10
0x18000ff93  comisd  xmm0, xmm9
0x18000ff98  jb      short loc_18000FFA9
0x18000ff9a  subsd   xmm0, xmm9
0x18000ff9f  comisd  xmm0, xmm9
0x18000ffa4  jnb     short loc_18000FFA9
0x18000ffa6  mov     rax, rcx
0x18000ffa9  cvttsd2si rcx, xmm0
0x18000ffae  add     rcx, rax
0x18000ffb1  jnz     short loc_18000FFBC
0x18000ffb3  comisd  xmm7, xmm8
0x18000ffb8  cmova   rcx, rdx
0x18000ffbc  mov     rax, [r14+r15]
0x18000ffc0  cmp     rcx, rax
0x18000ffc3  cmovbe  rax, rcx
0x18000ffc7  mov     rcx, [r14+r15+8]
0x18000ffcc  shl     rax, cl
0x18000ffcf  inc     r12
0x18000ffd2  or      rbx, rax
0x18000ffd5  mov     rcx, 8000000000000000h
0x18000ffdf  mov     [rsp+128h+var_F0], rbx
0x18000ffe4  cmp     r12, [r13+0]
0x18000ffe8  jb      loc_18000FF00
0x18000ffee  mov     r14, [rsp+128h+var_E8]
0x18000fff3  mov     r15, [rsp+128h+var_E0]
0x18000fff8  mov     rsi, rbx
0x18000fffb  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180010000  xor     edx, edx; dwFlags
0x180010002  test    eax, eax
0x180010004  jnz     loc_1800100B7
0x18001000a  mov     rcx, cs:gWfpHeap; hHeap
0x180010011  mov     r8d, 8; dwBytes
0x180010017  call    cs:__imp_HeapAlloc
0x18001001e  nop     dword ptr [rax+rax+00h]
0x180010023  mov     [r15+8], rax
0x180010027  test    rax, rax
0x18001002a  jz      loc_18001011D
0x180010030  xor     ebx, ebx
0x180010032  cmp     cs:gWfpTrackHeapBytes, ebx
0x180010038  jnz     loc_18001014F
0x18001003e  test    rbx, rbx
0x180010041  jnz     loc_18000FDAC
0x180010047  mov     rax, [r15+8]
0x18001004b  mov     dword ptr [r15], 4
0x180010052  mov     [rax], rsi
0x180010055  jmp     loc_18000FDD8
0x18001005a  test    cs:byte_1800F6115, 1
0x180010061  jz      loc_18000FE58
0x180010067  lea     rax, [rsp+128h+var_F0]
0x18001006c  mov     dword ptr [rsp+128h+var_F0], ebx
0x180010070  mov     [rsp+128h+var_B0], rax
0x180010075  lea     rdx, WFP_USERMODE_ERROR
0x18001007c  lea     rax, [rsp+128h+var_D0]
  ... truncated ...
```
