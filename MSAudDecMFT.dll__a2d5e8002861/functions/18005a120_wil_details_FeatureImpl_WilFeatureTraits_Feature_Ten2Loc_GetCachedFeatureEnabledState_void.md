# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18005a120`
- end: `0x18005a4a0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005cc00`

## callees

- `0x18003daf0`
- `0x18004dc52`
- `0x18004dd14`
- `0x18005a120`
- `0x18005ae40`
- `0x18005bc90`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a458`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a47c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a458`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18005a47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a311`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a402`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a402`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a1a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a354`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a1a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a354`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a17d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a299`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a17d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a3c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005a3c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005a3d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005a3d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(a1, &v30, &v29);
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
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v9, v6);
  }
  while ( v8 != v6 );
  if ( v10 || !wil::details::g_enabledStateManager )
    goto LABEL_32;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800E5E64 )
    goto LABEL_30;
  *(_QWORD *)&v28 = 3;
  *((_QWORD *)&v28 + 1) = Feature_Ten2Loc__descriptor;
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
  _InterlockedAnd((volatile signed __int32 *)Feature_Ten2Loc__descriptor, 0xFFFFFFFB);
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
0x18005a120  mov     [rsp+arg_10], rbx
0x18005a125  mov     [rsp+arg_0], rcx
0x18005a12a  push    rbp
0x18005a12b  push    rsi
0x18005a12c  push    rdi
0x18005a12d  push    r12
0x18005a12f  push    r13
0x18005a131  push    r14
0x18005a133  push    r15
0x18005a135  sub     rsp, 30h
0x18005a139  mov     rdi, rdx
0x18005a13c  mov     r14, cs:Feature_Ten2Loc__descriptor
0x18005a143  xor     r13d, r13d
0x18005a146  mov     [rdx], r13
0x18005a149  mov     eax, [r14]
0x18005a14c  mov     [rdx], eax
0x18005a14e  and     eax, 6
0x18005a151  cmp     al, 6
0x18005a153  jz      loc_18005A375
0x18005a159  mov     esi, cs:dword_1800E5E64
0x18005a15f  nop
0x18005a160  test    esi, esi
0x18005a162  jnz     loc_18005A216
0x18005a168  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a16e  test    eax, eax
0x18005a170  jz      loc_18005A213
0x18005a176  lea     rcx, SRWLock; SRWLock
0x18005a17d  call    cs:__imp_AcquireSRWLockExclusive
0x18005a184  nop     dword ptr [rax+rax+00h]
0x18005a189  cmp     cs:qword_1800E5EA8, r13
0x18005a190  jz      short loc_18005A1AE
0x18005a192  mov     esi, cs:dword_1800E5E64
0x18005a198  nop
0x18005a199  lea     rcx, SRWLock; SRWLock
0x18005a1a0  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a1a7  nop     dword ptr [rax+rax+00h]
0x18005a1ac  jmp     short loc_18005A216
0x18005a1ae  mov     cs:qword_1800E5EA8, r13
0x18005a1b5  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18005a1bc  test    rax, rax
0x18005a1bf  jnz     short loc_18005A1CD
0x18005a1c1  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18005a1c8  test    rax, rax
0x18005a1cb  jz      short loc_18005A200
0x18005a1cd  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a1d4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18005a1db  lea     rcx, qword_1800E5EA8
0x18005a1e2  call    cs:__guard_dispatch_icall_fptr
0x18005a1e8  cmp     cs:qword_1800E5EA8, 0
0x18005a1f0  jz      short loc_18005A200
0x18005a1f2  nop
0x18005a1f3  mov     esi, 1
0x18005a1f8  mov     cs:dword_1800E5E64, esi
0x18005a1fe  jmp     short loc_18005A199
0x18005a200  lea     rcx, SRWLock; SRWLock
0x18005a207  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a20e  nop     dword ptr [rax+rax+00h]
0x18005a213  mov     esi, r13d
0x18005a216  mov     dword ptr [rsp+68h+arg_0], r13d
0x18005a21b  lea     r8, [rsp+68h+arg_0]
0x18005a220  lea     rdx, [rsp+68h+arg_8]
0x18005a225  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18005a22a  mov     eax, [rdi]
0x18005a22c  mov     rbx, [rsp+68h+arg_8]
0x18005a231  mov     edx, eax
0x18005a233  mov     [rdi], eax
0x18005a235  mov     ecx, eax
0x18005a237  cmp     dword ptr [rsp+68h+arg_0], 0
0x18005a23c  jz      short loc_18005A257
0x18005a23e  test    dl, 2
0x18005a241  jnz     short loc_18005A257
0x18005a243  and     ecx, 0FFFFF63Eh
0x18005a249  mov     eax, ebx
0x18005a24b  and     eax, 9C1h
0x18005a250  or      ecx, eax
0x18005a252  or      ecx, 2
0x18005a255  mov     [rdi], ecx
0x18005a257  mov     r8d, edx
0x18005a25a  and     r8d, 4
0x18005a25e  jnz     short loc_18005A272
0x18005a260  btr     ecx, 0Ah
0x18005a264  mov     eax, ebx
0x18005a266  and     eax, 400h
0x18005a26b  or      ecx, eax
0x18005a26d  or      ecx, 4
0x18005a270  mov     [rdi], ecx
0x18005a272  mov     eax, edx
0x18005a274  lock cmpxchg [r14], ecx
0x18005a279  jnz     short loc_18005A231
0x18005a27b  test    r8d, r8d
0x18005a27e  jnz     loc_18005A360
0x18005a284  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a28a  test    eax, eax
0x18005a28c  jz      loc_18005A360
0x18005a292  lea     rcx, SRWLock; SRWLock
0x18005a299  call    cs:__imp_AcquireSRWLockExclusive
0x18005a2a0  nop     dword ptr [rax+rax+00h]
0x18005a2a5  mov     eax, cs:dword_1800E5E64
0x18005a2ab  test    esi, esi
0x18005a2ad  jz      loc_18005A348
0x18005a2b3  cmp     esi, eax
0x18005a2b5  jnz     loc_18005A348
0x18005a2bb  mov     qword ptr [rsp+68h+var_48], 3
0x18005a2c4  mov     qword ptr [rsp+68h+var_48+8], r14
0x18005a2c9  mov     r10, cs:qword_1800E5E98
0x18005a2d0  mov     rdx, r10
0x18005a2d3  sub     rdx, cs:Source
0x18005a2da  mov     r9, cs:qword_1800E5E90
0x18005a2e1  mov     rax, r9
0x18005a2e4  sub     rax, cs:Source
0x18005a2eb  add     rax, 10h
0x18005a2ef  cmp     rax, rdx
0x18005a2f2  jb      loc_18005A41D
0x18005a2f8  lea     rax, [rdx+rdx]
0x18005a2fc  mov     esi, 10h
0x18005a301  cmp     rax, rsi
0x18005a304  cmova   rsi, rax
0x18005a308  cmp     rdx, rsi
0x18005a30b  jnb     loc_18005A41D
0x18005a311  call    cs:__imp_GetLastError
0x18005a318  nop     dword ptr [rax+rax+00h]
0x18005a31d  mov     ebp, eax
0x18005a31f  and     rsi, 0FFFFFFFFFFFFFFC0h
0x18005a323  lea     r15, [rsi+40h]
0x18005a327  mov     rdx, r15; dwBytes
0x18005a32a  xor     ecx, ecx; dwFlags
0x18005a32c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18005a331  mov     rsi, rax
0x18005a334  test    rax, rax
0x18005a337  jnz     short loc_18005A391
0x18005a339  mov     ecx, ebp; dwErrCode
0x18005a33b  call    cs:__imp_SetLastError
0x18005a342  nop     dword ptr [rax+rax+00h]
0x18005a347  nop
0x18005a348  lock and dword ptr [r14], 0FFFFFFFBh
0x18005a34d  lea     rcx, SRWLock; SRWLock
0x18005a354  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a35b  nop     dword ptr [rax+rax+00h]
0x18005a360  mov     eax, [rdi]
0x18005a362  test    al, 2
0x18005a364  jnz     short loc_18005A375
0x18005a366  and     eax, 0FFFFF63Eh
0x18005a36b  and     ebx, 9C1h
0x18005a371  or      eax, ebx
0x18005a373  mov     [rdi], eax
0x18005a375  mov     rax, rdi
0x18005a378  mov     rbx, [rsp+68h+arg_10]
0x18005a380  add     rsp, 30h
0x18005a384  pop     r15
0x18005a386  pop     r14
0x18005a388  pop     r13
0x18005a38a  pop     r12
0x18005a38c  pop     rdi
0x18005a38d  pop     rsi
0x18005a38e  pop     rbp
0x18005a38f  retn
0x18005a391  mov     r8, cs:Source; Source
0x18005a398  mov     r14, cs:qword_1800E5E90
0x18005a39f  sub     r14, r8
0x18005a3a2  mov     r9, r14; SourceSize
0x18005a3a5  mov     rdx, r15; DestinationSize
0x18005a3a8  mov     rcx, rsi; Destination
0x18005a3ab  call    memcpy_s_0
0x18005a3b0  mov     r12, cs:lpMem
0x18005a3b7  mov     cs:lpMem, rsi
0x18005a3be  test    r12, r12
0x18005a3c1  jz      short loc_18005A3E3
0x18005a3c3  call    cs:__imp_GetProcessHeap
0x18005a3ca  nop     dword ptr [rax+rax+00h]
0x18005a3cf  mov     rcx, rax; hHeap
0x18005a3d2  mov     r8, r12; lpMem
0x18005a3d5  xor     edx, edx; dwFlags
0x18005a3d7  call    cs:__imp_HeapFree
0x18005a3de  nop     dword ptr [rax+rax+00h]
0x18005a3e3  mov     cs:Source, rsi
0x18005a3ea  lea     rax, [r14+rsi]
0x18005a3ee  mov     cs:qword_1800E5E90, rax
0x18005a3f5  lea     rax, [r15+rsi]
0x18005a3f9  mov     cs:qword_1800E5E98, rax
0x18005a400  mov     ecx, ebp; dwErrCode
0x18005a402  call    cs:__imp_SetLastError
0x18005a409  nop     dword ptr [rax+rax+00h]
0x18005a40e  nop
0x18005a40f  mov     r10, cs:qword_1800E5E98
0x18005a416  mov     r9, cs:qword_1800E5E90
0x18005a41d  mov     rax, r10
0x18005a420  sub     rax, r9
0x18005a423  mov     r8, r13
0x18005a426  cmp     r9, r10
0x18005a429  cmovb   r8, rax; Size
0x18005a42d  test    r9, r9
0x18005a430  jz      short loc_18005A47C
0x18005a432  cmp     r8, 10h
0x18005a436  jb      short loc_18005A44E
0x18005a438  movups  xmm0, [rsp+68h+var_48]
0x18005a43d  movups  xmmword ptr [r9], xmm0
0x18005a441  add     cs:qword_1800E5E90, 10h
0x18005a449  jmp     loc_18005A34D
0x18005a44e  xor     edx, edx; Val
0x18005a450  mov     rcx, r9; void *
0x18005a453  call    memset_0
0x18005a458  call    cs:__imp__o__errno
0x18005a45f  nop     dword ptr [rax+rax+00h]
0x18005a464  mov     dword ptr [rax], 22h ; '"'
0x18005a46a  call    _invalid_parameter_noinfo
0x18005a46f  add     cs:qword_1800E5E90, 10h
0x18005a477  jmp     loc_18005A34D
0x18005a47c  call    cs:__imp__o__errno
0x18005a483  nop     dword ptr [rax+rax+00h]
0x18005a488  mov     dword ptr [rax], 16h
0x18005a48e  call    _invalid_parameter_noinfo
0x18005a493  add     cs:qword_1800E5E90, 10h
0x18005a49b  jmp     loc_18005A34D
```
