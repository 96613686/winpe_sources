# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18005a590`
- end: `0x18005a910`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005cc80`

## callees

- `0x18003daf0`
- `0x18004dc52`
- `0x18004dd14`
- `0x18005a590`
- `0x18005b0b0`
- `0x18005bc90`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a8c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a8ec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a8c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a8ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a781`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a7ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a872`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a7ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a872`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a610`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a677`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a7c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a610`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a677`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a7c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a5ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a709`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a5ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005a847`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005a847`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // esi
  void (__fastcall *v5)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  int v10; // r8d
  __int64 v11; // rcx
  unsigned __int64 v12; // r10
  unsigned __int64 v13; // rdx
  _OWORD *v14; // r9
  unsigned __int64 v15; // rsi
  DWORD LastError; // ebp
  unsigned __int64 v17; // r15
  char *v18; // rax
  char *v19; // rsi
  char *v21; // r14
  void *v22; // r12
  HANDLE ProcessHeap; // rax
  size_t v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int128 v28; // [rsp+20h] [rbp-48h]
  __int64 v29; // [rsp+70h] [rbp+8h] BYREF
  __int64 v30; // [rsp+78h] [rbp+10h] BYREF

  v29 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = dword_1800E5E64;
  if ( !dword_1800E5E64 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800E5EA8 )
      {
        v4 = dword_1800E5E64;
LABEL_6:
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_13;
      }
      qword_1800E5EA8 = 0;
      v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v5(
          &qword_1800E5EA8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_1800E5EA8 )
        {
          v4 = 1;
          dword_1800E5E64 = 1;
          goto LABEL_6;
        }
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v4 = 0;
  }
LABEL_13:
  LODWORD(v29) = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(a1, &v30, &v29);
  v6 = *(_DWORD *)a2;
  v7 = v30;
  do
  {
    v8 = v6;
    *(_DWORD *)a2 = v6;
    v9 = v6;
    if ( (_DWORD)v29 && (v6 & 2) == 0 )
    {
      v9 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
      *(_DWORD *)a2 = v9;
    }
    v10 = v6 & 4;
    if ( (v6 & 4) == 0 )
    {
      v9 = v7 & 0x400 | v9 & 0xFFFFFBFF | 4;
      *(_DWORD *)a2 = v9;
    }
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v9, v6);
  }
  while ( v8 != v6 );
  if ( v10 || !wil::details::g_enabledStateManager )
    goto LABEL_32;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800E5E64 )
    goto LABEL_30;
  *(_QWORD *)&v28 = 3;
  *((_QWORD *)&v28 + 1) = Feature_TestLoc1Perf__descriptor;
  v12 = qword_1800E5E98;
  v13 = qword_1800E5E98 - Source;
  v14 = qword_1800E5E90;
  if ( (unsigned __int64)qword_1800E5E90 - Source + 16 < qword_1800E5E98 - Source )
    goto LABEL_38;
  v15 = 16;
  if ( 2 * v13 > 0x10 )
    v15 = 2 * v13;
  if ( v13 >= v15 )
  {
LABEL_38:
    v24 = 0;
    if ( (unsigned __int64)v14 < v12 )
      v24 = v12 - (_QWORD)v14;
    if ( v14 )
    {
      if ( v24 < 0x10 )
      {
        memset_0(v14, 0, v24);
        *(_DWORD *)_o__errno(v26, v25, v27) = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        *v14 = v28;
      }
      qword_1800E5E90 = (char *)qword_1800E5E90 + 16;
    }
    else
    {
      *(_DWORD *)_o__errno(v11, v13, v24) = 22;
      invalid_parameter_noinfo();
      qword_1800E5E90 = (char *)qword_1800E5E90 + 16;
    }
    goto LABEL_31;
  }
  LastError = GetLastError();
  v17 = (v15 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v18 = (char *)wil::details::ProcessHeapAlloc(0, v17);
  v19 = v18;
  if ( v18 )
  {
    v21 = (char *)qword_1800E5E90 - Source;
    memcpy_s_0(v18, v17, Source, (rsize_t)qword_1800E5E90 - Source);
    v22 = lpMem;
    lpMem = v19;
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    Source = v19;
    qword_1800E5E90 = &v19[(_QWORD)v21];
    qword_1800E5E98 = (__int64)&v19[v17];
    SetLastError(LastError);
    v12 = qword_1800E5E98;
    v14 = qword_1800E5E90;
    goto LABEL_38;
  }
  SetLastError(LastError);
LABEL_30:
  _InterlockedAnd((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, 0xFFFFFFFB);
LABEL_31:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_32:
  if ( (*(_DWORD *)a2 & 2) == 0 )
    *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  return a2;
}

```

## disassembly

```asm
0x18005a590  mov     [rsp+arg_10], rbx
0x18005a595  mov     [rsp+arg_0], rcx
0x18005a59a  push    rbp
0x18005a59b  push    rsi
0x18005a59c  push    rdi
0x18005a59d  push    r12
0x18005a59f  push    r13
0x18005a5a1  push    r14
0x18005a5a3  push    r15
0x18005a5a5  sub     rsp, 30h
0x18005a5a9  mov     rdi, rdx
0x18005a5ac  mov     r14, cs:Feature_TestLoc1Perf__descriptor
0x18005a5b3  xor     r13d, r13d
0x18005a5b6  mov     [rdx], r13
0x18005a5b9  mov     eax, [r14]
0x18005a5bc  mov     [rdx], eax
0x18005a5be  and     eax, 6
0x18005a5c1  cmp     al, 6
0x18005a5c3  jz      loc_18005A7E5
0x18005a5c9  mov     esi, cs:dword_1800E5E64
0x18005a5cf  nop
0x18005a5d0  test    esi, esi
0x18005a5d2  jnz     loc_18005A686
0x18005a5d8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a5de  test    eax, eax
0x18005a5e0  jz      loc_18005A683
0x18005a5e6  lea     rcx, SRWLock; SRWLock
0x18005a5ed  call    cs:__imp_AcquireSRWLockExclusive
0x18005a5f4  nop     dword ptr [rax+rax+00h]
0x18005a5f9  cmp     cs:qword_1800E5EA8, r13
0x18005a600  jz      short loc_18005A61E
0x18005a602  mov     esi, cs:dword_1800E5E64
0x18005a608  nop
0x18005a609  lea     rcx, SRWLock; SRWLock
0x18005a610  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a617  nop     dword ptr [rax+rax+00h]
0x18005a61c  jmp     short loc_18005A686
0x18005a61e  mov     cs:qword_1800E5EA8, r13
0x18005a625  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18005a62c  test    rax, rax
0x18005a62f  jnz     short loc_18005A63D
0x18005a631  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18005a638  test    rax, rax
0x18005a63b  jz      short loc_18005A670
0x18005a63d  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a644  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18005a64b  lea     rcx, qword_1800E5EA8
0x18005a652  call    cs:__guard_dispatch_icall_fptr
0x18005a658  cmp     cs:qword_1800E5EA8, 0
0x18005a660  jz      short loc_18005A670
0x18005a662  nop
0x18005a663  mov     esi, 1
0x18005a668  mov     cs:dword_1800E5E64, esi
0x18005a66e  jmp     short loc_18005A609
0x18005a670  lea     rcx, SRWLock; SRWLock
0x18005a677  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a67e  nop     dword ptr [rax+rax+00h]
0x18005a683  mov     esi, r13d
0x18005a686  mov     dword ptr [rsp+68h+arg_0], r13d
0x18005a68b  lea     r8, [rsp+68h+arg_0]
0x18005a690  lea     rdx, [rsp+68h+arg_8]
0x18005a695  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18005a69a  mov     eax, [rdi]
0x18005a69c  mov     rbx, [rsp+68h+arg_8]
0x18005a6a1  mov     edx, eax
0x18005a6a3  mov     [rdi], eax
0x18005a6a5  mov     ecx, eax
0x18005a6a7  cmp     dword ptr [rsp+68h+arg_0], 0
0x18005a6ac  jz      short loc_18005A6C7
0x18005a6ae  test    dl, 2
0x18005a6b1  jnz     short loc_18005A6C7
0x18005a6b3  and     ecx, 0FFFFF63Eh
0x18005a6b9  mov     eax, ebx
0x18005a6bb  and     eax, 9C1h
0x18005a6c0  or      ecx, eax
0x18005a6c2  or      ecx, 2
0x18005a6c5  mov     [rdi], ecx
0x18005a6c7  mov     r8d, edx
0x18005a6ca  and     r8d, 4
0x18005a6ce  jnz     short loc_18005A6E2
0x18005a6d0  btr     ecx, 0Ah
0x18005a6d4  mov     eax, ebx
0x18005a6d6  and     eax, 400h
0x18005a6db  or      ecx, eax
0x18005a6dd  or      ecx, 4
0x18005a6e0  mov     [rdi], ecx
0x18005a6e2  mov     eax, edx
0x18005a6e4  lock cmpxchg [r14], ecx
0x18005a6e9  jnz     short loc_18005A6A1
0x18005a6eb  test    r8d, r8d
0x18005a6ee  jnz     loc_18005A7D0
0x18005a6f4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a6fa  test    eax, eax
0x18005a6fc  jz      loc_18005A7D0
0x18005a702  lea     rcx, SRWLock; SRWLock
0x18005a709  call    cs:__imp_AcquireSRWLockExclusive
0x18005a710  nop     dword ptr [rax+rax+00h]
0x18005a715  mov     eax, cs:dword_1800E5E64
0x18005a71b  test    esi, esi
0x18005a71d  jz      loc_18005A7B8
0x18005a723  cmp     esi, eax
0x18005a725  jnz     loc_18005A7B8
0x18005a72b  mov     qword ptr [rsp+68h+var_48], 3
0x18005a734  mov     qword ptr [rsp+68h+var_48+8], r14
0x18005a739  mov     r10, cs:qword_1800E5E98
0x18005a740  mov     rdx, r10
0x18005a743  sub     rdx, cs:Source
0x18005a74a  mov     r9, cs:qword_1800E5E90
0x18005a751  mov     rax, r9
0x18005a754  sub     rax, cs:Source
0x18005a75b  add     rax, 10h
0x18005a75f  cmp     rax, rdx
0x18005a762  jb      loc_18005A88D
0x18005a768  lea     rax, [rdx+rdx]
0x18005a76c  mov     esi, 10h
0x18005a771  cmp     rax, rsi
0x18005a774  cmova   rsi, rax
0x18005a778  cmp     rdx, rsi
0x18005a77b  jnb     loc_18005A88D
0x18005a781  call    cs:__imp_GetLastError
0x18005a788  nop     dword ptr [rax+rax+00h]
0x18005a78d  mov     ebp, eax
0x18005a78f  and     rsi, 0FFFFFFFFFFFFFFC0h
0x18005a793  lea     r15, [rsi+40h]
0x18005a797  mov     rdx, r15; dwBytes
0x18005a79a  xor     ecx, ecx; dwFlags
0x18005a79c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18005a7a1  mov     rsi, rax
0x18005a7a4  test    rax, rax
0x18005a7a7  jnz     short loc_18005A801
0x18005a7a9  mov     ecx, ebp; dwErrCode
0x18005a7ab  call    cs:__imp_SetLastError
0x18005a7b2  nop     dword ptr [rax+rax+00h]
0x18005a7b7  nop
0x18005a7b8  lock and dword ptr [r14], 0FFFFFFFBh
0x18005a7bd  lea     rcx, SRWLock; SRWLock
0x18005a7c4  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a7cb  nop     dword ptr [rax+rax+00h]
0x18005a7d0  mov     eax, [rdi]
0x18005a7d2  test    al, 2
0x18005a7d4  jnz     short loc_18005A7E5
0x18005a7d6  and     eax, 0FFFFF63Eh
0x18005a7db  and     ebx, 9C1h
0x18005a7e1  or      eax, ebx
0x18005a7e3  mov     [rdi], eax
0x18005a7e5  mov     rax, rdi
0x18005a7e8  mov     rbx, [rsp+68h+arg_10]
0x18005a7f0  add     rsp, 30h
0x18005a7f4  pop     r15
0x18005a7f6  pop     r14
0x18005a7f8  pop     r13
0x18005a7fa  pop     r12
0x18005a7fc  pop     rdi
0x18005a7fd  pop     rsi
0x18005a7fe  pop     rbp
0x18005a7ff  retn
0x18005a801  mov     r8, cs:Source; Source
0x18005a808  mov     r14, cs:qword_1800E5E90
0x18005a80f  sub     r14, r8
0x18005a812  mov     r9, r14; SourceSize
0x18005a815  mov     rdx, r15; DestinationSize
0x18005a818  mov     rcx, rsi; Destination
0x18005a81b  call    memcpy_s_0
0x18005a820  mov     r12, cs:lpMem
0x18005a827  mov     cs:lpMem, rsi
0x18005a82e  test    r12, r12
0x18005a831  jz      short loc_18005A853
0x18005a833  call    cs:__imp_GetProcessHeap
0x18005a83a  nop     dword ptr [rax+rax+00h]
0x18005a83f  mov     rcx, rax; hHeap
0x18005a842  mov     r8, r12; lpMem
0x18005a845  xor     edx, edx; dwFlags
0x18005a847  call    cs:__imp_HeapFree
0x18005a84e  nop     dword ptr [rax+rax+00h]
0x18005a853  mov     cs:Source, rsi
0x18005a85a  lea     rax, [r14+rsi]
0x18005a85e  mov     cs:qword_1800E5E90, rax
0x18005a865  lea     rax, [r15+rsi]
0x18005a869  mov     cs:qword_1800E5E98, rax
0x18005a870  mov     ecx, ebp; dwErrCode
0x18005a872  call    cs:__imp_SetLastError
0x18005a879  nop     dword ptr [rax+rax+00h]
0x18005a87e  nop
0x18005a87f  mov     r10, cs:qword_1800E5E98
0x18005a886  mov     r9, cs:qword_1800E5E90
0x18005a88d  mov     rax, r10
0x18005a890  sub     rax, r9
0x18005a893  mov     r8, r13
0x18005a896  cmp     r9, r10
0x18005a899  cmovb   r8, rax; Size
0x18005a89d  test    r9, r9
0x18005a8a0  jz      short loc_18005A8EC
0x18005a8a2  cmp     r8, 10h
0x18005a8a6  jb      short loc_18005A8BE
0x18005a8a8  movups  xmm0, [rsp+68h+var_48]
0x18005a8ad  movups  xmmword ptr [r9], xmm0
0x18005a8b1  add     cs:qword_1800E5E90, 10h
0x18005a8b9  jmp     loc_18005A7BD
0x18005a8be  xor     edx, edx; Val
0x18005a8c0  mov     rcx, r9; void *
0x18005a8c3  call    memset_0
0x18005a8c8  call    cs:__imp__o__errno
0x18005a8cf  nop     dword ptr [rax+rax+00h]
0x18005a8d4  mov     dword ptr [rax], 22h ; '"'
0x18005a8da  call    _invalid_parameter_noinfo
0x18005a8df  add     cs:qword_1800E5E90, 10h
0x18005a8e7  jmp     loc_18005A7BD
0x18005a8ec  call    cs:__imp__o__errno
0x18005a8f3  nop     dword ptr [rax+rax+00h]
0x18005a8f8  mov     dword ptr [rax], 16h
0x18005a8fe  call    _invalid_parameter_noinfo
0x18005a903  add     cs:qword_1800E5E90, 10h
0x18005a90b  jmp     loc_18005A7BD
```
