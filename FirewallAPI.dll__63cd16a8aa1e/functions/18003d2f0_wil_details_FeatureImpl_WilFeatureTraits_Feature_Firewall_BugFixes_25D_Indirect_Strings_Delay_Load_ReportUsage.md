# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18003d2f0`
- end: `0x18003d7d4`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18003e5c0`

## callees

- `0x180024240`
- `0x1800277b0`
- `0x180028426`
- `0x1800284c4`
- `0x18003b370`
- `0x18003d2f0`
- `0x180040630`
- `0x180040978`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d534`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d563`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d534`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003d563`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d3e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d6ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d3e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d6ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d65d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d6ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d65d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d6ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d503`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d608`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d503`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d608`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d4d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d4d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d4de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d4de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d5da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d63d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d5da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003d63d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d5b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d5b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003d5f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003d5f1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d5e8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003d5e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::ReportUsage(
        __int64 a1,
        unsigned __int8 a2)
{
  unsigned int v2; // edi
  int v4; // r15d
  __int64 v5; // r12
  unsigned int v6; // esi
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  __int64 v9; // r8
  unsigned int v10; // r13d
  unsigned int v11; // ecx
  int v12; // edi
  __int64 v13; // rcx
  DWORD dwLowDateTime; // r11d
  unsigned __int64 v15; // r10
  unsigned __int64 v16; // rdx
  _DWORD *v17; // r9
  unsigned __int64 v18; // rbx
  DWORD LastError; // edi
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // r8
  char *v22; // rax
  char *v23; // rbx
  signed __int64 v24; // r14
  void *v25; // rbp
  HANDLE ProcessHeap; // rax
  size_t v27; // r8
  struct _TP_TIMER *v28; // rcx
  DWORD v29; // esi
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v31; // rdi
  DWORD v32; // ebx
  void (__fastcall *v33)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v34)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v35; // rdx
  void (__fastcall *v36)(__int64, __int64, _QWORD, _QWORD); // rax
  unsigned int v37; // [rsp+50h] [rbp-88h]
  int v38; // [rsp+54h] [rbp-84h]
  unsigned int v39; // [rsp+58h] [rbp-80h]
  unsigned int v40; // [rsp+5Ch] [rbp-7Ch]
  char v41[24]; // [rsp+60h] [rbp-78h] BYREF
  int v42; // [rsp+78h] [rbp-60h] BYREF
  __int16 v43; // [rsp+7Ch] [rbp-5Ch]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp-58h] BYREF
  __int64 v45; // [rsp+88h] [rbp-50h] BYREF

  v2 = a2;
  v4 = *(_DWORD *)Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load__descriptor;
  if ( (*(_DWORD *)Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load__descriptor & 4) == 0 )
  {
    v45 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetCachedFeatureEnabledState(
                       a1,
                       &pftDueTime);
    LOWORD(v4) = v45;
  }
  v42 = 0;
  v43 = 2;
  LODWORD(v45) = 3;
  v5 = a1 + 8;
  v6 = v2;
  v39 = v2;
  v7 = 4 * (v2 ^ 1) + 2;
  v37 = v7;
  v8 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v41, v5, v7);
  v10 = v8[1];
  v11 = v8[2];
  v40 = v11;
  v12 = v8[4];
  v38 = v12;
  if ( *v8 && wil::details::g_enabledStateManager && !wil::details::g_processShutdownInProgress )
  {
    if ( wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      goto LABEL_38;
    AcquireSRWLockExclusive(&stru_180097D68);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_37:
      ReleaseSRWLockExclusive(&stru_180097D68);
LABEL_38:
      v11 = v40;
      goto LABEL_39;
    }
    dwLowDateTime = 0;
    pftDueTime = 0;
    v15 = qword_180097D90;
    v16 = qword_180097D90 - (_QWORD)qword_180097D80;
    v17 = qword_180097D88;
    if ( (_BYTE *)qword_180097D88 - (_BYTE *)qword_180097D80 + 16 >= (unsigned __int64)(qword_180097D90
                                                                                      - (_QWORD)qword_180097D80) )
    {
      v18 = 16;
      if ( 2 * v16 > 0x10 )
        v18 = 2 * v16;
      if ( v16 < v18 )
      {
        LastError = GetLastError();
        v20 = (v18 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v22 = (char *)wil::details::ProcessHeapAlloc(0, v20, v21);
        v23 = v22;
        if ( !v22 )
        {
          SetLastError(LastError);
          goto LABEL_30;
        }
        v24 = (_BYTE *)qword_180097D88 - (_BYTE *)qword_180097D80;
        memcpy_s_0(v22, v20, qword_180097D80, (_BYTE *)qword_180097D88 - (_BYTE *)qword_180097D80);
        v25 = qword_180097D98;
        qword_180097D98 = v23;
        if ( v25 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
        }
        qword_180097D80 = v23;
        qword_180097D88 = &v23[v24];
        qword_180097D90 = (__int64)&v23[v20];
        SetLastError(LastError);
        v15 = qword_180097D90;
        v17 = qword_180097D88;
        dwLowDateTime = pftDueTime.dwLowDateTime;
      }
    }
    v27 = 0;
    if ( (unsigned __int64)v17 < v15 )
      v27 = v15 - (_QWORD)v17;
    if ( v17 )
    {
      if ( v27 >= 0x10 )
      {
        *v17 = 56414822;
        v17[1] = dwLowDateTime;
        *((_QWORD *)v17 + 1) = v5;
LABEL_29:
        qword_180097D88 = (char *)qword_180097D88 + 16;
LABEL_30:
        if ( !byte_180097D78 )
        {
          v28 = pti;
          if ( pti )
            goto LABEL_35;
          v29 = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              &wil::details::g_enabledStateManager,
                              0);
          v31 = pti;
          if ( pti )
          {
            v32 = GetLastError();
            SetThreadpoolTimer(v31, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v31, 1);
            CloseThreadpoolTimer(v31);
            SetLastError(v32);
          }
          pti = ThreadpoolTimer;
          SetLastError(v29);
          v28 = pti;
          if ( pti )
          {
LABEL_35:
            pftDueTime = (struct _FILETIME)-3000000000LL;
            SetThreadpoolTimer(v28, &pftDueTime, 0, 0x124F8u);
            byte_180097D78 = 1;
          }
        }
        v7 = v37;
        v12 = v38;
        v6 = v39;
        goto LABEL_37;
      }
      memset_0(v17, 0, v27);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v13, v16, v27) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_29;
  }
LABEL_39:
  if ( v10 )
  {
    v33 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v33 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v33(56414822, v11, v10, 0);
    }
  }
  if ( !v12 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_180097D68);
    if ( !qword_180097DC8 )
    {
      qword_180097DC8 = 0;
      v34 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v34 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v34(&qword_180097DC8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_180097D68);
  }
  if ( (v4 & 0x400) != 0 )
  {
    v35 = v7;
    if ( (v4 & 0x800) != 0 )
      v35 = v7 | 0x80000000;
    v36 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v36 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v36(56414822, v35, 0, 0);
    }
  }
  if ( !v12 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v9) = 2;
      g_wil_details_realtimeFeatureUsageHook(56414822, v7, v9);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(56414822, &v42, 0, v6, &v45, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x18003d2f0  mov     [rsp+arg_10], rbx
0x18003d2f5  push    rbp
0x18003d2f6  push    rsi
0x18003d2f7  push    rdi
0x18003d2f8  push    r12
0x18003d2fa  push    r13
0x18003d2fc  push    r14
0x18003d2fe  push    r15
0x18003d300  sub     rsp, 0A0h
0x18003d307  mov     rax, cs:__security_cookie
0x18003d30e  xor     rax, rsp
0x18003d311  mov     [rsp+0D8h+var_48], rax
0x18003d319  movzx   edi, dl
0x18003d31c  mov     rbx, rcx
0x18003d31f  mov     rax, cs:Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load__descriptor
0x18003d326  mov     r15d, [rax]
0x18003d329  test    r15b, 4
0x18003d32d  jnz     short loc_18003D34A
0x18003d32f  lea     rdx, [rsp+0D8h+pftDueTime]
0x18003d337  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetCachedFeatureEnabledState(void)
0x18003d33c  mov     rcx, [rax]
0x18003d33f  mov     [rsp+0D8h+var_50], rcx
0x18003d347  mov     r15d, ecx
0x18003d34a  xor     eax, eax
0x18003d34c  mov     [rsp+0D8h+var_60], eax
0x18003d350  mov     [rsp+0D8h+var_5C], 2
0x18003d357  mov     dword ptr [rsp+0D8h+var_50], 3
0x18003d362  lea     r12, [rbx+8]
0x18003d366  mov     esi, edi
0x18003d368  mov     [rsp+0D8h+var_80], edi
0x18003d36c  mov     eax, edi
0x18003d36e  xor     eax, 1
0x18003d371  lea     ebx, ds:2[rax*4]
0x18003d378  mov     [rsp+0D8h+var_88], ebx
0x18003d37c  mov     r8d, ebx
0x18003d37f  mov     rdx, r12
0x18003d382  lea     rcx, [rsp+0D8h+var_78]
0x18003d387  call    wil_details_FeatureReporting_RecordUsageInCache
0x18003d38c  mov     r13d, [rax+4]
0x18003d390  mov     ecx, [rax+8]
0x18003d393  mov     [rsp+0D8h+var_7C], ecx
0x18003d397  mov     edi, [rax+10h]
0x18003d39a  mov     [rsp+0D8h+var_84], edi
0x18003d39e  cmp     dword ptr [rax], 0
0x18003d3a1  jz      loc_18003D667
0x18003d3a7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003d3ad  test    eax, eax
0x18003d3af  jz      loc_18003D667
0x18003d3b5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003d3bc  jnz     loc_18003D667
0x18003d3c2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003d3c9  test    rax, rax
0x18003d3cc  jz      short loc_18003D3DB
0x18003d3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3d3  test    al, al
0x18003d3d5  jnz     loc_18003D663
0x18003d3db  lea     rcx, stru_180097D68; SRWLock
0x18003d3e2  call    cs:__imp_AcquireSRWLockExclusive
0x18003d3e8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003d3ee  test    eax, eax
0x18003d3f0  jz      loc_18003D656
0x18003d3f6  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003d3fd  jnz     loc_18003D656
0x18003d403  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003d40a  test    rax, rax
0x18003d40d  jz      short loc_18003D41C
0x18003d40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d414  test    al, al
0x18003d416  jnz     loc_18003D656
0x18003d41c  xor     r11d, r11d
0x18003d41f  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], r11
0x18003d427  mov     r10, cs:qword_180097D90
0x18003d42e  mov     rdx, r10
0x18003d431  sub     rdx, cs:qword_180097D80
0x18003d438  mov     r9, cs:qword_180097D88
0x18003d43f  mov     rax, r9
0x18003d442  sub     rax, cs:qword_180097D80
0x18003d449  add     rax, 10h
0x18003d44d  cmp     rax, rdx
0x18003d450  jb      loc_18003D51F
0x18003d456  lea     rax, [rdx+rdx]
0x18003d45a  mov     ebx, 10h
0x18003d45f  cmp     rax, rbx
0x18003d462  cmova   rbx, rax
0x18003d466  cmp     rdx, rbx
0x18003d469  jnb     loc_18003D51F
0x18003d46f  call    cs:__imp_GetLastError
0x18003d475  mov     edi, eax
0x18003d477  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18003d47b  lea     rsi, [rbx+40h]
0x18003d47f  mov     rdx, rsi; dwBytes
0x18003d482  xor     ecx, ecx; dwFlags
0x18003d484  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003d489  mov     rbx, rax
0x18003d48c  test    rax, rax
0x18003d48f  jnz     short loc_18003D49E
0x18003d491  mov     ecx, edi; dwErrCode
0x18003d493  call    cs:__imp_SetLastError
0x18003d499  jmp     loc_18003D57C
0x18003d49e  mov     r8, cs:qword_180097D80; Source
0x18003d4a5  mov     r14, cs:qword_180097D88
0x18003d4ac  sub     r14, r8
0x18003d4af  mov     r9, r14; SourceSize
0x18003d4b2  mov     rdx, rsi; DestinationSize
0x18003d4b5  mov     rcx, rbx; Destination
0x18003d4b8  call    memcpy_s_0
0x18003d4bd  mov     rbp, cs:qword_180097D98
0x18003d4c4  mov     cs:qword_180097D98, rbx
0x18003d4cb  test    rbp, rbp
0x18003d4ce  jz      short loc_18003D4E4
0x18003d4d0  call    cs:__imp_GetProcessHeap
0x18003d4d6  mov     rcx, rax; hHeap
0x18003d4d9  mov     r8, rbp; lpMem
0x18003d4dc  xor     edx, edx; dwFlags
0x18003d4de  call    cs:__imp_HeapFree
0x18003d4e4  mov     cs:qword_180097D80, rbx
0x18003d4eb  lea     rax, [r14+rbx]
0x18003d4ef  mov     cs:qword_180097D88, rax
0x18003d4f6  lea     rax, [rsi+rbx]
0x18003d4fa  mov     cs:qword_180097D90, rax
0x18003d501  mov     ecx, edi; dwErrCode
0x18003d503  call    cs:__imp_SetLastError
0x18003d509  mov     r10, cs:qword_180097D90
0x18003d510  mov     r9, cs:qword_180097D88
0x18003d517  mov     r11, qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime]
0x18003d51f  mov     rax, r10
0x18003d522  sub     rax, r9
0x18003d525  xor     r8d, r8d
0x18003d528  cmp     r9, r10
0x18003d52b  cmovb   r8, rax; Size
0x18003d52f  test    r9, r9
0x18003d532  jnz     short loc_18003D542
0x18003d534  call    cs:__imp__o__errno
0x18003d53a  mov     dword ptr [rax], 16h
0x18003d540  jmp     short loc_18003D56F
0x18003d542  cmp     r8, 10h
0x18003d546  jb      short loc_18003D559
0x18003d548  mov     dword ptr [r9], 35CD266h
0x18003d54f  mov     [r9+4], r11d
0x18003d553  mov     [r9+8], r12
0x18003d557  jmp     short loc_18003D574
0x18003d559  xor     edx, edx; Val
0x18003d55b  mov     rcx, r9; void *
0x18003d55e  call    memset_0
0x18003d563  call    cs:__imp__o__errno
0x18003d569  mov     dword ptr [rax], 22h ; '"'
0x18003d56f  call    _invalid_parameter_noinfo
0x18003d574  add     cs:qword_180097D88, 10h
0x18003d57c  cmp     cs:byte_180097D78, 0
0x18003d583  jnz     loc_18003D64A
0x18003d589  mov     rcx, cs:pti
0x18003d590  test    rcx, rcx
0x18003d593  jnz     loc_18003D61A
0x18003d599  call    cs:__imp_GetLastError
0x18003d59f  mov     esi, eax
0x18003d5a1  xor     r8d, r8d; pcbe
0x18003d5a4  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18003d5ab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003d5b2  call    cs:__imp_CreateThreadpoolTimer
0x18003d5b8  mov     rbp, rax
0x18003d5bb  mov     rdi, cs:pti
0x18003d5c2  test    rdi, rdi
0x18003d5c5  jz      short loc_18003D5FF
0x18003d5c7  call    cs:__imp_GetLastError
0x18003d5cd  mov     ebx, eax
0x18003d5cf  xor     r9d, r9d; msWindowLength
0x18003d5d2  xor     r8d, r8d; msPeriod
0x18003d5d5  xor     edx, edx; pftDueTime
0x18003d5d7  mov     rcx, rdi; pti
0x18003d5da  call    cs:__imp_SetThreadpoolTimer
0x18003d5e0  mov     edx, 1; fCancelPendingCallbacks
0x18003d5e5  mov     rcx, rdi; pti
0x18003d5e8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003d5ee  mov     rcx, rdi; pti
0x18003d5f1  call    cs:__imp_CloseThreadpoolTimer
0x18003d5f7  mov     ecx, ebx; dwErrCode
0x18003d5f9  call    cs:__imp_SetLastError
0x18003d5ff  mov     cs:pti, rbp
0x18003d606  mov     ecx, esi; dwErrCode
0x18003d608  call    cs:__imp_SetLastError
0x18003d60e  mov     rcx, cs:pti; pti
0x18003d615  test    rcx, rcx
0x18003d618  jz      short loc_18003D64A
0x18003d61a  mov     rax, 0FFFFFFFF4D2FA200h
0x18003d624  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18003d62c  mov     r9d, 124F8h; msWindowLength
0x18003d632  xor     r8d, r8d; msPeriod
0x18003d635  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18003d63d  call    cs:__imp_SetThreadpoolTimer
0x18003d643  mov     cs:byte_180097D78, 1
0x18003d64a  mov     ebx, [rsp+0D8h+var_88]
0x18003d64e  mov     edi, [rsp+0D8h+var_84]
0x18003d652  mov     esi, [rsp+0D8h+var_80]
0x18003d656  lea     rcx, stru_180097D68; SRWLock
0x18003d65d  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d663  mov     ecx, [rsp+0D8h+var_7C]
0x18003d667  test    r13d, r13d
0x18003d66a  jz      short loc_18003D696
0x18003d66c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18003d673  test    rax, rax
0x18003d676  jnz     short loc_18003D684
0x18003d678  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18003d67f  test    rax, rax
0x18003d682  jz      short loc_18003D696
0x18003d684  mov     edx, ecx
0x18003d686  xor     r9d, r9d
0x18003d689  mov     r8d, r13d
0x18003d68c  mov     ecx, 35CD266h
0x18003d691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d696  test    edi, edi
0x18003d698  jnz     short loc_18003D706
0x18003d69a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003d6a0  test    eax, eax
0x18003d6a2  jz      short loc_18003D706
0x18003d6a4  lea     rcx, stru_180097D68; SRWLock
0x18003d6ab  call    cs:__imp_AcquireSRWLockExclusive
0x18003d6b1  cmp     cs:qword_180097DC8, 0
0x18003d6b9  jnz     short loc_18003D6F8
0x18003d6bb  mov     cs:qword_180097DC8, 0
0x18003d6c6  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18003d6cd  test    rax, rax
0x18003d6d0  jnz     short loc_18003D6DE
0x18003d6d2  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18003d6d9  test    rax, rax
0x18003d6dc  jz      short loc_18003D6F8
0x18003d6de  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18003d6e5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18003d6ec  lea     rcx, qword_180097DC8
0x18003d6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6f8  lea     rcx, stru_180097D68; SRWLock
0x18003d6ff  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d705  nop
0x18003d706  bt      r15d, 0Ah
0x18003d70b  jnb     short loc_18003D745
0x18003d70d  mov     eax, ebx
0x18003d70f  bts     eax, 1Fh
0x18003d713  mov     edx, ebx
0x18003d715  bt      r15d, 0Bh
0x18003d71a  cmovb   edx, eax
0x18003d71d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18003d724  test    rax, rax
0x18003d727  jnz     short loc_18003D735
0x18003d729  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18003d730  test    rax, rax
0x18003d733  jz      short loc_18003D745
0x18003d735  xor     r9d, r9d
0x18003d738  xor     r8d, r8d
0x18003d73b  mov     ecx, 35CD266h
0x18003d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d745  test    edi, edi
0x18003d747  jnz     short loc_18003D7A9
0x18003d749  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18003d750  test    rax, rax
0x18003d753  jz      short loc_18003D764
0x18003d755  mov     r8b, 2
0x18003d758  mov     edx, ebx
0x18003d75a  mov     ecx, 35CD266h
0x18003d75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d764  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18003d76b  test    rax, rax
0x18003d76e  jz      short loc_18003D7A9
0x18003d770  mov     [rsp+0D8h+var_A0], 1
0x18003d779  mov     [rsp+0D8h+var_A8], 0
0x18003d77e  mov     [rsp+0D8h+var_B0], 0
0x18003d787  lea     rdx, [rsp+0D8h+var_50]
0x18003d78f  mov     [rsp+0D8h+var_B8], rdx
0x18003d794  mov     r9d, esi
0x18003d797  xor     r8d, r8d
0x18003d79a  lea     rdx, [rsp+0D8h+var_60]
0x18003d79f  mov     ecx, 35CD266h
0x18003d7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7a9  mov     rcx, [rsp+0D8h+var_48]
0x18003d7b1  xor     rcx, rsp; StackCookie
0x18003d7b4  call    __security_check_cookie
0x18003d7b9  mov     rbx, [rsp+0D8h+arg_10]
0x18003d7c1  add     rsp, 0A0h
0x18003d7c8  pop     r15
0x18003d7ca  pop     r14
0x18003d7cc  pop     r13
0x18003d7ce  pop     r12
0x18003d7d0  pop     rdi
0x18003d7d1  pop     rsi
0x18003d7d2  pop     rbp
0x18003d7d3  retn
```
