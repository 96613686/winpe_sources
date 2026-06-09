# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18004d610`
- end: `0x18004db6d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004db80`

## callees

- `0x180025dd0`
- `0x1800294b0`
- `0x18002a156`
- `0x18002a1f4`
- `0x1800437f0`
- `0x180043b54`
- `0x18004c180`
- `0x18004d610`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004d878`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004d8ad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004d878`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004d8ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d702`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004da37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d702`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004da37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d9e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004da91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d9e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004da91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d923`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d7bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d841`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d96d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d982`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d7bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d841`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d96d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d982`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d802`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d802`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d816`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d816`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004d93c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004d9bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004d93c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004d9bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004d908`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004d908`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004d95f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004d95f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004d950`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004d950`

## pseudocode

```c
void __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::ReportUsage(
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
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  struct _TP_TIMER *v31; // rcx
  DWORD v32; // esi
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v34; // rdi
  DWORD v35; // ebx
  void (__fastcall *v36)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v37)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v38; // rdx
  void (__fastcall *v39)(__int64, __int64, _QWORD, _QWORD); // rax
  unsigned int v40; // [rsp+50h] [rbp-88h]
  int v41; // [rsp+54h] [rbp-84h]
  unsigned int v42; // [rsp+58h] [rbp-80h]
  unsigned int v43; // [rsp+5Ch] [rbp-7Ch]
  char v44[24]; // [rsp+60h] [rbp-78h] BYREF
  int v45; // [rsp+78h] [rbp-60h] BYREF
  __int16 v46; // [rsp+7Ch] [rbp-5Ch]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp-58h] BYREF
  __int64 v48; // [rsp+88h] [rbp-50h] BYREF

  v2 = a2;
  v4 = *(_DWORD *)Feature_Firewall_New_ZTN_Audit_Events__descriptor;
  if ( (*(_DWORD *)Feature_Firewall_New_ZTN_Audit_Events__descriptor & 4) == 0 )
  {
    v48 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetCachedFeatureEnabledState(
                       a1,
                       &pftDueTime);
    LOWORD(v4) = v48;
  }
  v45 = 0;
  v46 = 1;
  LODWORD(v48) = 3;
  v5 = a1 + 8;
  v6 = v2;
  v42 = v2;
  v7 = 4 * (v2 ^ 1) + 2;
  v40 = v7;
  v8 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v44, v5, v7);
  v10 = v8[1];
  v11 = v8[2];
  v43 = v11;
  v12 = v8[4];
  v41 = v12;
  if ( *v8 && wil::details::g_enabledStateManager && !wil::details::g_processShutdownInProgress )
  {
    if ( wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      goto LABEL_38;
    AcquireSRWLockExclusive(&stru_18009BCE0);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_37:
      ReleaseSRWLockExclusive(&stru_18009BCE0);
LABEL_38:
      v11 = v43;
      goto LABEL_39;
    }
    dwLowDateTime = 0;
    pftDueTime = 0;
    v15 = qword_18009BD18;
    v16 = qword_18009BD18 - (_QWORD)qword_18009BD08;
    v17 = qword_18009BD10;
    if ( (_BYTE *)qword_18009BD10 - (_BYTE *)qword_18009BD08 + 16 >= (unsigned __int64)(qword_18009BD18
                                                                                      - (_QWORD)qword_18009BD08) )
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
        v24 = (_BYTE *)qword_18009BD10 - (_BYTE *)qword_18009BD08;
        memcpy_s_0(v22, v20, qword_18009BD08, (_BYTE *)qword_18009BD10 - (_BYTE *)qword_18009BD08);
        v25 = qword_18009BD20;
        qword_18009BD20 = v23;
        if ( v25 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
        }
        qword_18009BD08 = v23;
        qword_18009BD10 = &v23[v24];
        qword_18009BD18 = (__int64)&v23[v20];
        SetLastError(LastError);
        v15 = qword_18009BD18;
        v17 = qword_18009BD10;
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
        *v17 = 56336450;
        v17[1] = dwLowDateTime;
        *((_QWORD *)v17 + 1) = v5;
LABEL_29:
        qword_18009BD10 = (char *)qword_18009BD10 + 16;
LABEL_30:
        if ( !byte_18009BCF0 )
        {
          v31 = pti;
          if ( pti )
            goto LABEL_35;
          v32 = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              &wil::details::g_enabledStateManager,
                              0);
          v34 = pti;
          if ( pti )
          {
            v35 = GetLastError();
            SetThreadpoolTimer(v34, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v34, 1);
            CloseThreadpoolTimer(v34);
            SetLastError(v35);
          }
          pti = ThreadpoolTimer;
          SetLastError(v32);
          v31 = pti;
          if ( pti )
          {
LABEL_35:
            pftDueTime = (struct _FILETIME)-3000000000LL;
            SetThreadpoolTimer(v31, &pftDueTime, 0, 0x124F8u);
            byte_18009BCF0 = 1;
          }
        }
        v7 = v40;
        v12 = v41;
        v6 = v42;
        goto LABEL_37;
      }
      memset_0(v17, 0, v27);
      *(_DWORD *)_o__errno(v29, v28, v30) = 34;
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
    v36 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v36 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v36(56336450, v11, v10, 0);
    }
  }
  if ( !v12 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_18009BCE0);
    if ( !qword_18009BD00 )
    {
      qword_18009BD00 = 0;
      v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v37(&qword_18009BD00, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_18009BCE0);
  }
  if ( (v4 & 0x400) != 0 )
  {
    v38 = v7;
    if ( (v4 & 0x800) != 0 )
      v38 = v7 | 0x80000000;
    v39 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v39 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v39(56336450, v38, 0, 0);
    }
  }
  if ( !v12 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v9) = 1;
      g_wil_details_realtimeFeatureUsageHook(56336450, v7, v9);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(56336450, &v45, 0, v6, &v48, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x18004d610  mov     [rsp+arg_10], rbx
0x18004d615  push    rbp
0x18004d616  push    rsi
0x18004d617  push    rdi
0x18004d618  push    r12
0x18004d61a  push    r13
0x18004d61c  push    r14
0x18004d61e  push    r15
0x18004d620  sub     rsp, 0A0h
0x18004d627  mov     rax, cs:__security_cookie
0x18004d62e  xor     rax, rsp
0x18004d631  mov     [rsp+0D8h+var_48], rax
0x18004d639  movzx   edi, dl
0x18004d63c  mov     rbx, rcx
0x18004d63f  mov     rax, cs:Feature_Firewall_New_ZTN_Audit_Events__descriptor
0x18004d646  mov     r15d, [rax]
0x18004d649  test    r15b, 4
0x18004d64d  jnz     short loc_18004D66A
0x18004d64f  lea     rdx, [rsp+0D8h+pftDueTime]
0x18004d657  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_New_ZTN_Audit_Events>::GetCachedFeatureEnabledState(void)
0x18004d65c  mov     rcx, [rax]
0x18004d65f  mov     [rsp+0D8h+var_50], rcx
0x18004d667  mov     r15d, ecx
0x18004d66a  xor     eax, eax
0x18004d66c  mov     [rsp+0D8h+var_60], eax
0x18004d670  mov     [rsp+0D8h+var_5C], 1
0x18004d677  mov     dword ptr [rsp+0D8h+var_50], 3
0x18004d682  lea     r12, [rbx+8]
0x18004d686  mov     esi, edi
0x18004d688  mov     [rsp+0D8h+var_80], edi
0x18004d68c  mov     eax, edi
0x18004d68e  xor     eax, 1
0x18004d691  lea     ebx, ds:2[rax*4]
0x18004d698  mov     [rsp+0D8h+var_88], ebx
0x18004d69c  mov     r8d, ebx
0x18004d69f  mov     rdx, r12
0x18004d6a2  lea     rcx, [rsp+0D8h+var_78]
0x18004d6a7  call    wil_details_FeatureReporting_RecordUsageInCache
0x18004d6ac  mov     r13d, [rax+4]
0x18004d6b0  mov     ecx, [rax+8]
0x18004d6b3  mov     [rsp+0D8h+var_7C], ecx
0x18004d6b7  mov     edi, [rax+10h]
0x18004d6ba  mov     [rsp+0D8h+var_84], edi
0x18004d6be  cmp     dword ptr [rax], 0
0x18004d6c1  jz      loc_18004D9F3
0x18004d6c7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004d6cd  test    eax, eax
0x18004d6cf  jz      loc_18004D9F3
0x18004d6d5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004d6dc  jnz     loc_18004D9F3
0x18004d6e2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18004d6e9  test    rax, rax
0x18004d6ec  jz      short loc_18004D6FB
0x18004d6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6f3  test    al, al
0x18004d6f5  jnz     loc_18004D9EF
0x18004d6fb  lea     rcx, stru_18009BCE0; SRWLock
0x18004d702  call    cs:__imp_AcquireSRWLockExclusive
0x18004d709  nop     dword ptr [rax+rax+00h]
0x18004d70e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004d714  test    eax, eax
0x18004d716  jz      loc_18004D9DC
0x18004d71c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004d723  jnz     loc_18004D9DC
0x18004d729  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18004d730  test    rax, rax
0x18004d733  jz      short loc_18004D742
0x18004d735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d73a  test    al, al
0x18004d73c  jnz     loc_18004D9DC
0x18004d742  xor     r11d, r11d
0x18004d745  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], r11
0x18004d74d  mov     r10, cs:qword_18009BD18
0x18004d754  mov     rdx, r10
0x18004d757  sub     rdx, cs:qword_18009BD08
0x18004d75e  mov     r9, cs:qword_18009BD10
0x18004d765  mov     rax, r9
0x18004d768  sub     rax, cs:qword_18009BD08
0x18004d76f  add     rax, 10h
0x18004d773  cmp     rax, rdx
0x18004d776  jb      loc_18004D863
0x18004d77c  lea     rax, [rdx+rdx]
0x18004d780  mov     ebx, 10h
0x18004d785  cmp     rax, rbx
0x18004d788  cmova   rbx, rax
0x18004d78c  cmp     rdx, rbx
0x18004d78f  jnb     loc_18004D863
0x18004d795  call    cs:__imp_GetLastError
0x18004d79c  nop     dword ptr [rax+rax+00h]
0x18004d7a1  mov     edi, eax
0x18004d7a3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18004d7a7  lea     rsi, [rbx+40h]
0x18004d7ab  mov     rdx, rsi; dwBytes
0x18004d7ae  xor     ecx, ecx; dwFlags
0x18004d7b0  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18004d7b5  mov     rbx, rax
0x18004d7b8  test    rax, rax
0x18004d7bb  jnz     short loc_18004D7D0
0x18004d7bd  mov     ecx, edi; dwErrCode
0x18004d7bf  call    cs:__imp_SetLastError
0x18004d7c6  nop     dword ptr [rax+rax+00h]
0x18004d7cb  jmp     loc_18004D8CC
0x18004d7d0  mov     r8, cs:qword_18009BD08; Source
0x18004d7d7  mov     r14, cs:qword_18009BD10
0x18004d7de  sub     r14, r8
0x18004d7e1  mov     r9, r14; SourceSize
0x18004d7e4  mov     rdx, rsi; DestinationSize
0x18004d7e7  mov     rcx, rbx; Destination
0x18004d7ea  call    memcpy_s_0
0x18004d7ef  mov     rbp, cs:qword_18009BD20
0x18004d7f6  mov     cs:qword_18009BD20, rbx
0x18004d7fd  test    rbp, rbp
0x18004d800  jz      short loc_18004D822
0x18004d802  call    cs:__imp_GetProcessHeap
0x18004d809  nop     dword ptr [rax+rax+00h]
0x18004d80e  mov     rcx, rax; hHeap
0x18004d811  mov     r8, rbp; lpMem
0x18004d814  xor     edx, edx; dwFlags
0x18004d816  call    cs:__imp_HeapFree
0x18004d81d  nop     dword ptr [rax+rax+00h]
0x18004d822  mov     cs:qword_18009BD08, rbx
0x18004d829  lea     rax, [r14+rbx]
0x18004d82d  mov     cs:qword_18009BD10, rax
0x18004d834  lea     rax, [rsi+rbx]
0x18004d838  mov     cs:qword_18009BD18, rax
0x18004d83f  mov     ecx, edi; dwErrCode
0x18004d841  call    cs:__imp_SetLastError
0x18004d848  nop     dword ptr [rax+rax+00h]
0x18004d84d  mov     r10, cs:qword_18009BD18
0x18004d854  mov     r9, cs:qword_18009BD10
0x18004d85b  mov     r11, qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime]
0x18004d863  mov     rax, r10
0x18004d866  sub     rax, r9
0x18004d869  xor     r8d, r8d
0x18004d86c  cmp     r9, r10
0x18004d86f  cmovb   r8, rax; Size
0x18004d873  test    r9, r9
0x18004d876  jnz     short loc_18004D88C
0x18004d878  call    cs:__imp__o__errno
0x18004d87f  nop     dword ptr [rax+rax+00h]
0x18004d884  mov     dword ptr [rax], 16h
0x18004d88a  jmp     short loc_18004D8BF
0x18004d88c  cmp     r8, 10h
0x18004d890  jb      short loc_18004D8A3
0x18004d892  mov     dword ptr [r9], 35BA042h
0x18004d899  mov     [r9+4], r11d
0x18004d89d  mov     [r9+8], r12
0x18004d8a1  jmp     short loc_18004D8C4
0x18004d8a3  xor     edx, edx; Val
0x18004d8a5  mov     rcx, r9; void *
0x18004d8a8  call    memset_0
0x18004d8ad  call    cs:__imp__o__errno
0x18004d8b4  nop     dword ptr [rax+rax+00h]
0x18004d8b9  mov     dword ptr [rax], 22h ; '"'
0x18004d8bf  call    _invalid_parameter_noinfo
0x18004d8c4  add     cs:qword_18009BD10, 10h
0x18004d8cc  cmp     cs:byte_18009BCF0, 0
0x18004d8d3  jnz     loc_18004D9D0
0x18004d8d9  mov     rcx, cs:pti
0x18004d8e0  test    rcx, rcx
0x18004d8e3  jnz     loc_18004D99A
0x18004d8e9  call    cs:__imp_GetLastError
0x18004d8f0  nop     dword ptr [rax+rax+00h]
0x18004d8f5  mov     esi, eax
0x18004d8f7  xor     r8d, r8d; pcbe
0x18004d8fa  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18004d901  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004d908  call    cs:__imp_CreateThreadpoolTimer
0x18004d90f  nop     dword ptr [rax+rax+00h]
0x18004d914  mov     rbp, rax
0x18004d917  mov     rdi, cs:pti
0x18004d91e  test    rdi, rdi
0x18004d921  jz      short loc_18004D979
0x18004d923  call    cs:__imp_GetLastError
0x18004d92a  nop     dword ptr [rax+rax+00h]
0x18004d92f  mov     ebx, eax
0x18004d931  xor     r9d, r9d; msWindowLength
0x18004d934  xor     r8d, r8d; msPeriod
0x18004d937  xor     edx, edx; pftDueTime
0x18004d939  mov     rcx, rdi; pti
0x18004d93c  call    cs:__imp_SetThreadpoolTimer
0x18004d943  nop     dword ptr [rax+rax+00h]
0x18004d948  mov     edx, 1; fCancelPendingCallbacks
0x18004d94d  mov     rcx, rdi; pti
0x18004d950  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004d957  nop     dword ptr [rax+rax+00h]
0x18004d95c  mov     rcx, rdi; pti
0x18004d95f  call    cs:__imp_CloseThreadpoolTimer
0x18004d966  nop     dword ptr [rax+rax+00h]
0x18004d96b  mov     ecx, ebx; dwErrCode
0x18004d96d  call    cs:__imp_SetLastError
0x18004d974  nop     dword ptr [rax+rax+00h]
0x18004d979  mov     cs:pti, rbp
0x18004d980  mov     ecx, esi; dwErrCode
0x18004d982  call    cs:__imp_SetLastError
0x18004d989  nop     dword ptr [rax+rax+00h]
0x18004d98e  mov     rcx, cs:pti; pti
0x18004d995  test    rcx, rcx
0x18004d998  jz      short loc_18004D9D0
0x18004d99a  mov     rax, 0FFFFFFFF4D2FA200h
0x18004d9a4  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18004d9ac  mov     r9d, 124F8h; msWindowLength
0x18004d9b2  xor     r8d, r8d; msPeriod
0x18004d9b5  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18004d9bd  call    cs:__imp_SetThreadpoolTimer
0x18004d9c4  nop     dword ptr [rax+rax+00h]
0x18004d9c9  mov     cs:byte_18009BCF0, 1
0x18004d9d0  mov     ebx, [rsp+0D8h+var_88]
0x18004d9d4  mov     edi, [rsp+0D8h+var_84]
0x18004d9d8  mov     esi, [rsp+0D8h+var_80]
0x18004d9dc  lea     rcx, stru_18009BCE0; SRWLock
0x18004d9e3  call    cs:__imp_ReleaseSRWLockExclusive
0x18004d9ea  nop     dword ptr [rax+rax+00h]
0x18004d9ef  mov     ecx, [rsp+0D8h+var_7C]
0x18004d9f3  test    r13d, r13d
0x18004d9f6  jz      short loc_18004DA22
0x18004d9f8  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18004d9ff  test    rax, rax
0x18004da02  jnz     short loc_18004DA10
0x18004da04  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18004da0b  test    rax, rax
0x18004da0e  jz      short loc_18004DA22
0x18004da10  mov     edx, ecx
0x18004da12  xor     r9d, r9d
0x18004da15  mov     r8d, r13d
0x18004da18  mov     ecx, 35BA042h
0x18004da1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da22  test    edi, edi
0x18004da24  jnz     short loc_18004DA9E
0x18004da26  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004da2c  test    eax, eax
0x18004da2e  jz      short loc_18004DA9E
0x18004da30  lea     rcx, stru_18009BCE0; SRWLock
0x18004da37  call    cs:__imp_AcquireSRWLockExclusive
0x18004da3e  nop     dword ptr [rax+rax+00h]
0x18004da43  cmp     cs:qword_18009BD00, 0
0x18004da4b  jnz     short loc_18004DA8A
0x18004da4d  mov     cs:qword_18009BD00, 0
0x18004da58  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18004da5f  test    rax, rax
0x18004da62  jnz     short loc_18004DA70
0x18004da64  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18004da6b  test    rax, rax
0x18004da6e  jz      short loc_18004DA8A
0x18004da70  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18004da77  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18004da7e  lea     rcx, qword_18009BD00
0x18004da85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da8a  lea     rcx, stru_18009BCE0; SRWLock
0x18004da91  call    cs:__imp_ReleaseSRWLockExclusive
0x18004da98  nop     dword ptr [rax+rax+00h]
0x18004da9d  nop
0x18004da9e  bt      r15d, 0Ah
0x18004daa3  jnb     short loc_18004DADD
0x18004daa5  mov     eax, ebx
0x18004daa7  bts     eax, 1Fh
0x18004daab  mov     edx, ebx
0x18004daad  bt      r15d, 0Bh
0x18004dab2  cmovb   edx, eax
0x18004dab5  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18004dabc  test    rax, rax
0x18004dabf  jnz     short loc_18004DACD
0x18004dac1  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18004dac8  test    rax, rax
0x18004dacb  jz      short loc_18004DADD
0x18004dacd  xor     r9d, r9d
0x18004dad0  xor     r8d, r8d
0x18004dad3  mov     ecx, 35BA042h
0x18004dad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dadd  test    edi, edi
0x18004dadf  jnz     short loc_18004DB41
0x18004dae1  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18004dae8  test    rax, rax
0x18004daeb  jz      short loc_18004DAFC
0x18004daed  mov     r8b, 1
0x18004daf0  mov     edx, ebx
0x18004daf2  mov     ecx, 35BA042h
0x18004daf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dafc  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18004db03  test    rax, rax
0x18004db06  jz      short loc_18004DB41
0x18004db08  mov     [rsp+0D8h+var_A0], 1
0x18004db11  mov     [rsp+0D8h+var_A8], 0
0x18004db16  mov     [rsp+0D8h+var_B0], 0
0x18004db1f  lea     rdx, [rsp+0D8h+var_50]
0x18004db27  mov     [rsp+0D8h+var_B8], rdx
0x18004db2c  mov     r9d, esi
0x18004db2f  xor     r8d, r8d
0x18004db32  lea     rdx, [rsp+0D8h+var_60]
0x18004db37  mov     ecx, 35BA042h
0x18004db3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db41  mov     rcx, [rsp+0D8h+var_48]
0x18004db49  xor     rcx, rsp; StackCookie
0x18004db4c  call    __security_check_cookie
0x18004db51  mov     rbx, [rsp+0D8h+arg_10]
0x18004db59  add     rsp, 0A0h
0x18004db60  pop     r15
0x18004db62  pop     r14
0x18004db64  pop     r13
0x18004db66  pop     r12
  ... truncated ...
```
