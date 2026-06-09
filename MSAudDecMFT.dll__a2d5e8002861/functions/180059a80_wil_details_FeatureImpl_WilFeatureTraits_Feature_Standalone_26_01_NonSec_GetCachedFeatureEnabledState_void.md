# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180059a80`
- end: `0x180059e90`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `1040`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005b0b0`

## callees

- `0x18003daf0`
- `0x18004dc52`
- `0x18004dd14`
- `0x180059a80`
- `0x18005bc90`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180059e48`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180059e6c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180059e48`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180059e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059cf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059df2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059df2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059afc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059afc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059d36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059ad9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059c7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059ad9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059c7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059db3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180059db3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180059dc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180059dc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // esi
  void (__fastcall *v5)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // rax
  int v7; // eax
  __int16 v8; // cx
  __int16 v9; // bx
  unsigned __int16 v10; // bx
  int v11; // eax
  signed __int32 v12; // edx
  signed __int32 v13; // ecx
  __int64 v14; // rcx
  unsigned __int64 v15; // r10
  unsigned __int64 v16; // rdx
  _OWORD *v17; // r9
  unsigned __int64 v18; // rsi
  DWORD LastError; // ebp
  unsigned __int64 v20; // r15
  char *v21; // rax
  char *v22; // rsi
  int v23; // ecx
  char *v25; // r14
  void *v26; // r12
  HANDLE ProcessHeap; // rax
  size_t v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int128 v32; // [rsp+20h] [rbp-58h]
  __int64 v33; // [rsp+80h] [rbp+8h] BYREF

  v33 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
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
  LODWORD(v33) = 0;
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_internalGetFeatureEnabledState;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v8 = 0;
      goto LABEL_20;
    }
  }
  v7 = v6(58599532, 3, &v33);
  v8 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
  if ( (v7 & 0xFFFFFF3F) == 0 )
  {
LABEL_20:
    v9 = 64;
    goto LABEL_21;
  }
  v9 = 0;
  if ( (v7 & 0xFFFFFF3F) == 2 )
    v9 = 64;
LABEL_21:
  v10 = v8 | v9;
  v11 = *(_DWORD *)a2;
  do
  {
    v12 = v11;
    *(_DWORD *)a2 = v11;
    if ( (_DWORD)v33 && (v11 & 2) == 0 )
    {
      v11 = (v11
           ^ ((unsigned __int16)v11
            ^ v10)
           & 0x180
           ^ ((unsigned __int8)v10
            ^ (unsigned __int8)(v11 ^ (v11 ^ v10) & 0x80))
           & 0x40
           | 1)
          ^ (((unsigned __int16)(v11
                               ^ (v11
                                ^ v10)
                               & 0x180
                               ^ ((unsigned __int8)v10
                                ^ (unsigned __int8)(v11 ^ (v11 ^ v10) & 0x80))
                               & 0x40)
            | 1)
           ^ v10)
          & 0x800
          | 2;
      *(_DWORD *)a2 = v11;
    }
    if ( (v12 & 4) != 0 )
    {
      v13 = v11;
    }
    else
    {
      v13 = v11 ^ ((unsigned __int16)v11 ^ v10) & 0x400 | 4;
      *(_DWORD *)a2 = v13;
    }
    v11 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v13, v12);
  }
  while ( v12 != v11 );
  if ( (v12 & 4) != 0 || !wil::details::g_enabledStateManager )
    goto LABEL_41;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800E5E64 )
    goto LABEL_39;
  *(_QWORD *)&v32 = 3;
  *((_QWORD *)&v32 + 1) = Feature_Standalone_26_01_NonSec__descriptor;
  v15 = qword_1800E5E98;
  v16 = qword_1800E5E98 - Source;
  v17 = qword_1800E5E90;
  if ( (unsigned __int64)qword_1800E5E90 - Source + 16 < qword_1800E5E98 - Source )
    goto LABEL_47;
  v18 = 16;
  if ( 2 * v16 > 0x10 )
    v18 = 2 * v16;
  if ( v16 >= v18 )
  {
LABEL_47:
    v28 = 0;
    if ( (unsigned __int64)v17 < v15 )
      v28 = v15 - (_QWORD)v17;
    if ( v17 )
    {
      if ( v28 < 0x10 )
      {
        memset_0(v17, 0, v28);
        *(_DWORD *)_o__errno(v30, v29, v31) = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        *v17 = v32;
      }
      qword_1800E5E90 = (char *)qword_1800E5E90 + 16;
    }
    else
    {
      *(_DWORD *)_o__errno(v14, v16, v28) = 22;
      invalid_parameter_noinfo();
      qword_1800E5E90 = (char *)qword_1800E5E90 + 16;
    }
    goto LABEL_40;
  }
  LastError = GetLastError();
  v20 = (v18 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v21 = (char *)wil::details::ProcessHeapAlloc(0, v20);
  v22 = v21;
  if ( v21 )
  {
    v25 = (char *)qword_1800E5E90 - Source;
    memcpy_s_0(v21, v20, Source, (rsize_t)qword_1800E5E90 - Source);
    v26 = lpMem;
    lpMem = v22;
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    Source = v22;
    qword_1800E5E90 = &v22[(_QWORD)v25];
    qword_1800E5E98 = (__int64)&v22[v20];
    SetLastError(LastError);
    v15 = qword_1800E5E98;
    v17 = qword_1800E5E90;
    goto LABEL_47;
  }
  SetLastError(LastError);
LABEL_39:
  _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, 0xFFFFFFFB);
LABEL_40:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_41:
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v23 = *(_DWORD *)a2
        ^ ((unsigned __int16)*(_DWORD *)a2
         ^ v10)
        & 0x180
        ^ ((unsigned __int8)(*(_DWORD *)a2 ^ (*(_DWORD *)a2 ^ v10) & 0x80)
         ^ (unsigned __int8)v10)
        & 0x40
        | 1;
    *(_DWORD *)a2 = v23 ^ ((unsigned __int16)v23 ^ v10) & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180059a80  mov     [rsp+arg_0], rcx
0x180059a85  push    rbx
0x180059a86  push    rbp
0x180059a87  push    rsi
0x180059a88  push    rdi
0x180059a89  push    r12
0x180059a8b  push    r13
0x180059a8d  push    r14
0x180059a8f  push    r15
0x180059a91  sub     rsp, 38h
0x180059a95  mov     rdi, rdx
0x180059a98  mov     r14, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180059a9f  xor     r13d, r13d
0x180059aa2  mov     [rdx], r13
0x180059aa5  mov     eax, [r14]
0x180059aa8  mov     [rdx], eax
0x180059aaa  and     eax, 6
0x180059aad  cmp     al, 6
0x180059aaf  jz      loc_180059D6C
0x180059ab5  mov     esi, cs:dword_1800E5E64
0x180059abb  nop
0x180059abc  test    esi, esi
0x180059abe  jnz     loc_180059B72
0x180059ac4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059aca  test    eax, eax
0x180059acc  jz      loc_180059B6F
0x180059ad2  lea     rcx, SRWLock; SRWLock
0x180059ad9  call    cs:__imp_AcquireSRWLockExclusive
0x180059ae0  nop     dword ptr [rax+rax+00h]
0x180059ae5  cmp     cs:qword_1800E5EA8, r13
0x180059aec  jz      short loc_180059B0A
0x180059aee  mov     esi, cs:dword_1800E5E64
0x180059af4  nop
0x180059af5  lea     rcx, SRWLock; SRWLock
0x180059afc  call    cs:__imp_ReleaseSRWLockExclusive
0x180059b03  nop     dword ptr [rax+rax+00h]
0x180059b08  jmp     short loc_180059B72
0x180059b0a  mov     cs:qword_1800E5EA8, r13
0x180059b11  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180059b18  test    rax, rax
0x180059b1b  jnz     short loc_180059B29
0x180059b1d  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180059b24  test    rax, rax
0x180059b27  jz      short loc_180059B5C
0x180059b29  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059b30  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180059b37  lea     rcx, qword_1800E5EA8
0x180059b3e  call    cs:__guard_dispatch_icall_fptr
0x180059b44  cmp     cs:qword_1800E5EA8, 0
0x180059b4c  jz      short loc_180059B5C
0x180059b4e  nop
0x180059b4f  mov     esi, 1
0x180059b54  mov     cs:dword_1800E5E64, esi
0x180059b5a  jmp     short loc_180059AF5
0x180059b5c  lea     rcx, SRWLock; SRWLock
0x180059b63  call    cs:__imp_ReleaseSRWLockExclusive
0x180059b6a  nop     dword ptr [rax+rax+00h]
0x180059b6f  mov     esi, r13d
0x180059b72  mov     dword ptr [rsp+78h+arg_0], r13d
0x180059b7a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180059b81  test    rax, rax
0x180059b84  jnz     short loc_180059B92
0x180059b86  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180059b8d  test    rax, rax
0x180059b90  jz      short loc_180059BEC
0x180059b92  lea     r8, [rsp+78h+arg_0]
0x180059b9a  mov     edx, 3
0x180059b9f  mov     ecx, 37E286Ch
0x180059ba4  call    cs:__guard_dispatch_icall_fptr
0x180059baa  mov     edx, eax
0x180059bac  mov     r8d, eax
0x180059baf  and     r8d, 0FFFFFF3Fh
0x180059bb6  mov     ecx, r8d
0x180059bb9  and     ecx, 3
0x180059bbc  shl     ecx, 2
0x180059bbf  and     eax, 40h
0x180059bc2  or      ecx, eax
0x180059bc4  shl     ecx, 2
0x180059bc7  and     edx, 80h
0x180059bcd  or      ecx, edx
0x180059bcf  lea     ecx, ds:0[rcx*8]
0x180059bd6  test    r8d, r8d
0x180059bd9  jz      short loc_180059BEF
0x180059bdb  mov     ebx, r13d
0x180059bde  mov     eax, 40h ; '@'
0x180059be3  cmp     r8d, 2
0x180059be7  cmovz   ebx, eax
0x180059bea  jmp     short loc_180059BF4
0x180059bec  mov     ecx, r13d
0x180059bef  mov     ebx, 40h ; '@'
0x180059bf4  or      ebx, ecx
0x180059bf6  mov     eax, [rdi]
0x180059bf8  mov     edx, eax
0x180059bfa  mov     [rdi], eax
0x180059bfc  cmp     dword ptr [rsp+78h+arg_0], 0
0x180059c04  jz      short loc_180059C34
0x180059c06  test    dl, 2
0x180059c09  jnz     short loc_180059C34
0x180059c0b  mov     eax, ebx
0x180059c0d  xor     eax, edx
0x180059c0f  and     eax, 180h
0x180059c14  xor     eax, edx
0x180059c16  mov     ecx, eax
0x180059c18  xor     ecx, ebx
0x180059c1a  and     ecx, 40h
0x180059c1d  xor     ecx, eax
0x180059c1f  or      ecx, 1
0x180059c22  mov     eax, ebx
0x180059c24  xor     eax, ecx
0x180059c26  and     eax, 800h
0x180059c2b  xor     eax, ecx
0x180059c2d  or      eax, 2
0x180059c30  mov     [rdi], eax
0x180059c32  jmp     short loc_180059C36
0x180059c34  mov     eax, edx
0x180059c36  mov     r8d, edx
0x180059c39  and     r8d, 4
0x180059c3d  jnz     short loc_180059C52
0x180059c3f  mov     ecx, ebx
0x180059c41  xor     ecx, eax
0x180059c43  and     ecx, 400h
0x180059c49  xor     ecx, eax
0x180059c4b  or      ecx, 4
0x180059c4e  mov     [rdi], ecx
0x180059c50  jmp     short loc_180059C54
0x180059c52  mov     ecx, eax
0x180059c54  mov     eax, edx
0x180059c56  lock cmpxchg [r14], ecx
0x180059c5b  jnz     short loc_180059BF8
0x180059c5d  test    r8d, r8d
0x180059c60  jnz     loc_180059D42
0x180059c66  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059c6c  test    eax, eax
0x180059c6e  jz      loc_180059D42
0x180059c74  lea     rcx, SRWLock; SRWLock
0x180059c7b  call    cs:__imp_AcquireSRWLockExclusive
0x180059c82  nop     dword ptr [rax+rax+00h]
0x180059c87  mov     eax, cs:dword_1800E5E64
0x180059c8d  test    esi, esi
0x180059c8f  jz      loc_180059D2A
0x180059c95  cmp     esi, eax
0x180059c97  jnz     loc_180059D2A
0x180059c9d  mov     qword ptr [rsp+78h+var_58], 3
0x180059ca6  mov     qword ptr [rsp+78h+var_58+8], r14
0x180059cab  mov     r10, cs:qword_1800E5E98
0x180059cb2  mov     rdx, r10
0x180059cb5  sub     rdx, cs:Source
0x180059cbc  mov     r9, cs:qword_1800E5E90
0x180059cc3  mov     rax, r9
0x180059cc6  sub     rax, cs:Source
0x180059ccd  add     rax, 10h
0x180059cd1  cmp     rax, rdx
0x180059cd4  jb      loc_180059E0D
0x180059cda  lea     rax, [rdx+rdx]
0x180059cde  mov     esi, 10h
0x180059ce3  cmp     rax, rsi
0x180059ce6  cmova   rsi, rax
0x180059cea  cmp     rdx, rsi
0x180059ced  jnb     loc_180059E0D
0x180059cf3  call    cs:__imp_GetLastError
0x180059cfa  nop     dword ptr [rax+rax+00h]
0x180059cff  mov     ebp, eax
0x180059d01  and     rsi, 0FFFFFFFFFFFFFFC0h
0x180059d05  lea     r15, [rsi+40h]
0x180059d09  mov     rdx, r15; dwBytes
0x180059d0c  xor     ecx, ecx; dwFlags
0x180059d0e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180059d13  mov     rsi, rax
0x180059d16  test    rax, rax
0x180059d19  jnz     short loc_180059D81
0x180059d1b  mov     ecx, ebp; dwErrCode
0x180059d1d  call    cs:__imp_SetLastError
0x180059d24  nop     dword ptr [rax+rax+00h]
0x180059d29  nop
0x180059d2a  lock and dword ptr [r14], 0FFFFFFFBh
0x180059d2f  lea     rcx, SRWLock; SRWLock
0x180059d36  call    cs:__imp_ReleaseSRWLockExclusive
0x180059d3d  nop     dword ptr [rax+rax+00h]
0x180059d42  mov     ecx, [rdi]
0x180059d44  test    cl, 2
0x180059d47  jnz     short loc_180059D6C
0x180059d49  mov     eax, ebx
0x180059d4b  xor     eax, ecx
0x180059d4d  and     eax, 180h
0x180059d52  xor     eax, ecx
0x180059d54  mov     ecx, ebx
0x180059d56  xor     ecx, eax
0x180059d58  and     ecx, 40h
0x180059d5b  xor     ecx, eax
0x180059d5d  or      ecx, 1
0x180059d60  xor     ebx, ecx
0x180059d62  and     ebx, 800h
0x180059d68  xor     ebx, ecx
0x180059d6a  mov     [rdi], ebx
0x180059d6c  mov     rax, rdi
0x180059d6f  add     rsp, 38h
0x180059d73  pop     r15
0x180059d75  pop     r14
0x180059d77  pop     r13
0x180059d79  pop     r12
0x180059d7b  pop     rdi
0x180059d7c  pop     rsi
0x180059d7d  pop     rbp
0x180059d7e  pop     rbx
0x180059d7f  retn
0x180059d81  mov     r8, cs:Source; Source
0x180059d88  mov     r14, cs:qword_1800E5E90
0x180059d8f  sub     r14, r8
0x180059d92  mov     r9, r14; SourceSize
0x180059d95  mov     rdx, r15; DestinationSize
0x180059d98  mov     rcx, rsi; Destination
0x180059d9b  call    memcpy_s_0
0x180059da0  mov     r12, cs:lpMem
0x180059da7  mov     cs:lpMem, rsi
0x180059dae  test    r12, r12
0x180059db1  jz      short loc_180059DD3
0x180059db3  call    cs:__imp_GetProcessHeap
0x180059dba  nop     dword ptr [rax+rax+00h]
0x180059dbf  mov     rcx, rax; hHeap
0x180059dc2  mov     r8, r12; lpMem
0x180059dc5  xor     edx, edx; dwFlags
0x180059dc7  call    cs:__imp_HeapFree
0x180059dce  nop     dword ptr [rax+rax+00h]
0x180059dd3  mov     cs:Source, rsi
0x180059dda  lea     rax, [r14+rsi]
0x180059dde  mov     cs:qword_1800E5E90, rax
0x180059de5  lea     rax, [r15+rsi]
0x180059de9  mov     cs:qword_1800E5E98, rax
0x180059df0  mov     ecx, ebp; dwErrCode
0x180059df2  call    cs:__imp_SetLastError
0x180059df9  nop     dword ptr [rax+rax+00h]
0x180059dfe  nop
0x180059dff  mov     r10, cs:qword_1800E5E98
0x180059e06  mov     r9, cs:qword_1800E5E90
0x180059e0d  mov     rax, r10
0x180059e10  sub     rax, r9
0x180059e13  mov     r8, r13
0x180059e16  cmp     r9, r10
0x180059e19  cmovb   r8, rax; Size
0x180059e1d  test    r9, r9
0x180059e20  jz      short loc_180059E6C
0x180059e22  cmp     r8, 10h
0x180059e26  jb      short loc_180059E3E
0x180059e28  movups  xmm0, [rsp+78h+var_58]
0x180059e2d  movups  xmmword ptr [r9], xmm0
0x180059e31  add     cs:qword_1800E5E90, 10h
0x180059e39  jmp     loc_180059D2F
0x180059e3e  xor     edx, edx; Val
0x180059e40  mov     rcx, r9; void *
0x180059e43  call    memset_0
0x180059e48  call    cs:__imp__o__errno
0x180059e4f  nop     dword ptr [rax+rax+00h]
0x180059e54  mov     dword ptr [rax], 22h ; '"'
0x180059e5a  call    _invalid_parameter_noinfo
0x180059e5f  add     cs:qword_1800E5E90, 10h
0x180059e67  jmp     loc_180059D2F
0x180059e6c  call    cs:__imp__o__errno
0x180059e73  nop     dword ptr [rax+rax+00h]
0x180059e78  mov     dword ptr [rax], 16h
0x180059e7e  call    _invalid_parameter_noinfo
0x180059e83  add     cs:qword_1800E5E90, 10h
0x180059e8b  jmp     loc_180059D2F
```
