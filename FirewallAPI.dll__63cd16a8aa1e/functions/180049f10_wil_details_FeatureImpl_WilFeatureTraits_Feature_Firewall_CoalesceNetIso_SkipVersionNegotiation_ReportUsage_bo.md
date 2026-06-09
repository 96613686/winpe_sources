# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180049f10`
- end: `0x18004a3f4`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004a8f0`

## callees

- `0x180024240`
- `0x1800277b0`
- `0x180028426`
- `0x1800284c4`
- `0x180040630`
- `0x180040978`
- `0x180048760`
- `0x180049f10`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004a154`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004a183`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004a154`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004a183`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a002`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a2cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a002`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a2cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a27d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a31f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a27d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a31f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a0b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a123`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a228`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a0b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a123`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a228`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a0f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a0f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a0fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a0fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004a1fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004a25d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004a1fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004a25d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004a1d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004a1d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004a211`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004a211`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004a208`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004a208`

## pseudocode

```c
void __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::ReportUsage(
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
  v4 = *(_DWORD *)Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation__descriptor;
  if ( (*(_DWORD *)Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation__descriptor & 4) == 0 )
  {
    v48 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::GetCachedFeatureEnabledState(
                       a1,
                       &pftDueTime);
    LOWORD(v4) = v48;
  }
  v45 = 0;
  v46 = 2;
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
    AcquireSRWLockExclusive(&stru_180097D68);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_37:
      ReleaseSRWLockExclusive(&stru_180097D68);
LABEL_38:
      v11 = v43;
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
        *v17 = 61893217;
        v17[1] = dwLowDateTime;
        *((_QWORD *)v17 + 1) = v5;
LABEL_29:
        qword_180097D88 = (char *)qword_180097D88 + 16;
LABEL_30:
        if ( !byte_180097D78 )
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
            byte_180097D78 = 1;
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
      v36(61893217, v11, v10, 0);
    }
  }
  if ( !v12 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_180097D68);
    if ( !qword_180097DC8 )
    {
      qword_180097DC8 = 0;
      v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v37(&qword_180097DC8, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&stru_180097D68);
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
      v39(61893217, v38, 0, 0);
    }
  }
  if ( !v12 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(v9) = 2;
      g_wil_details_realtimeFeatureUsageHook(61893217, v7, v9);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(61893217, &v45, 0, v6, &v48, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x180049f10  mov     [rsp+arg_10], rbx
0x180049f15  push    rbp
0x180049f16  push    rsi
0x180049f17  push    rdi
0x180049f18  push    r12
0x180049f1a  push    r13
0x180049f1c  push    r14
0x180049f1e  push    r15
0x180049f20  sub     rsp, 0A0h
0x180049f27  mov     rax, cs:__security_cookie
0x180049f2e  xor     rax, rsp
0x180049f31  mov     [rsp+0D8h+var_48], rax
0x180049f39  movzx   edi, dl
0x180049f3c  mov     rbx, rcx
0x180049f3f  mov     rax, cs:Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation__descriptor
0x180049f46  mov     r15d, [rax]
0x180049f49  test    r15b, 4
0x180049f4d  jnz     short loc_180049F6A
0x180049f4f  lea     rdx, [rsp+0D8h+pftDueTime]
0x180049f57  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_CoalesceNetIso_SkipVersionNegotiation>::GetCachedFeatureEnabledState(void)
0x180049f5c  mov     rcx, [rax]
0x180049f5f  mov     [rsp+0D8h+var_50], rcx
0x180049f67  mov     r15d, ecx
0x180049f6a  xor     eax, eax
0x180049f6c  mov     [rsp+0D8h+var_60], eax
0x180049f70  mov     [rsp+0D8h+var_5C], 2
0x180049f77  mov     dword ptr [rsp+0D8h+var_50], 3
0x180049f82  lea     r12, [rbx+8]
0x180049f86  mov     esi, edi
0x180049f88  mov     [rsp+0D8h+var_80], edi
0x180049f8c  mov     eax, edi
0x180049f8e  xor     eax, 1
0x180049f91  lea     ebx, ds:2[rax*4]
0x180049f98  mov     [rsp+0D8h+var_88], ebx
0x180049f9c  mov     r8d, ebx
0x180049f9f  mov     rdx, r12
0x180049fa2  lea     rcx, [rsp+0D8h+var_78]
0x180049fa7  call    wil_details_FeatureReporting_RecordUsageInCache
0x180049fac  mov     r13d, [rax+4]
0x180049fb0  mov     ecx, [rax+8]
0x180049fb3  mov     [rsp+0D8h+var_7C], ecx
0x180049fb7  mov     edi, [rax+10h]
0x180049fba  mov     [rsp+0D8h+var_84], edi
0x180049fbe  cmp     dword ptr [rax], 0
0x180049fc1  jz      loc_18004A287
0x180049fc7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180049fcd  test    eax, eax
0x180049fcf  jz      loc_18004A287
0x180049fd5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180049fdc  jnz     loc_18004A287
0x180049fe2  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180049fe9  test    rax, rax
0x180049fec  jz      short loc_180049FFB
0x180049fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ff3  test    al, al
0x180049ff5  jnz     loc_18004A283
0x180049ffb  lea     rcx, stru_180097D68; SRWLock
0x18004a002  call    cs:__imp_AcquireSRWLockExclusive
0x18004a008  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004a00e  test    eax, eax
0x18004a010  jz      loc_18004A276
0x18004a016  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18004a01d  jnz     loc_18004A276
0x18004a023  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18004a02a  test    rax, rax
0x18004a02d  jz      short loc_18004A03C
0x18004a02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a034  test    al, al
0x18004a036  jnz     loc_18004A276
0x18004a03c  xor     r11d, r11d
0x18004a03f  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], r11
0x18004a047  mov     r10, cs:qword_180097D90
0x18004a04e  mov     rdx, r10
0x18004a051  sub     rdx, cs:qword_180097D80
0x18004a058  mov     r9, cs:qword_180097D88
0x18004a05f  mov     rax, r9
0x18004a062  sub     rax, cs:qword_180097D80
0x18004a069  add     rax, 10h
0x18004a06d  cmp     rax, rdx
0x18004a070  jb      loc_18004A13F
0x18004a076  lea     rax, [rdx+rdx]
0x18004a07a  mov     ebx, 10h
0x18004a07f  cmp     rax, rbx
0x18004a082  cmova   rbx, rax
0x18004a086  cmp     rdx, rbx
0x18004a089  jnb     loc_18004A13F
0x18004a08f  call    cs:__imp_GetLastError
0x18004a095  mov     edi, eax
0x18004a097  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18004a09b  lea     rsi, [rbx+40h]
0x18004a09f  mov     rdx, rsi; dwBytes
0x18004a0a2  xor     ecx, ecx; dwFlags
0x18004a0a4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18004a0a9  mov     rbx, rax
0x18004a0ac  test    rax, rax
0x18004a0af  jnz     short loc_18004A0BE
0x18004a0b1  mov     ecx, edi; dwErrCode
0x18004a0b3  call    cs:__imp_SetLastError
0x18004a0b9  jmp     loc_18004A19C
0x18004a0be  mov     r8, cs:qword_180097D80; Source
0x18004a0c5  mov     r14, cs:qword_180097D88
0x18004a0cc  sub     r14, r8
0x18004a0cf  mov     r9, r14; SourceSize
0x18004a0d2  mov     rdx, rsi; DestinationSize
0x18004a0d5  mov     rcx, rbx; Destination
0x18004a0d8  call    memcpy_s_0
0x18004a0dd  mov     rbp, cs:qword_180097D98
0x18004a0e4  mov     cs:qword_180097D98, rbx
0x18004a0eb  test    rbp, rbp
0x18004a0ee  jz      short loc_18004A104
0x18004a0f0  call    cs:__imp_GetProcessHeap
0x18004a0f6  mov     rcx, rax; hHeap
0x18004a0f9  mov     r8, rbp; lpMem
0x18004a0fc  xor     edx, edx; dwFlags
0x18004a0fe  call    cs:__imp_HeapFree
0x18004a104  mov     cs:qword_180097D80, rbx
0x18004a10b  lea     rax, [r14+rbx]
0x18004a10f  mov     cs:qword_180097D88, rax
0x18004a116  lea     rax, [rsi+rbx]
0x18004a11a  mov     cs:qword_180097D90, rax
0x18004a121  mov     ecx, edi; dwErrCode
0x18004a123  call    cs:__imp_SetLastError
0x18004a129  mov     r10, cs:qword_180097D90
0x18004a130  mov     r9, cs:qword_180097D88
0x18004a137  mov     r11, qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime]
0x18004a13f  mov     rax, r10
0x18004a142  sub     rax, r9
0x18004a145  xor     r8d, r8d
0x18004a148  cmp     r9, r10
0x18004a14b  cmovb   r8, rax; Size
0x18004a14f  test    r9, r9
0x18004a152  jnz     short loc_18004A162
0x18004a154  call    cs:__imp__o__errno
0x18004a15a  mov     dword ptr [rax], 16h
0x18004a160  jmp     short loc_18004A18F
0x18004a162  cmp     r8, 10h
0x18004a166  jb      short loc_18004A179
0x18004a168  mov     dword ptr [r9], 3B06A61h
0x18004a16f  mov     [r9+4], r11d
0x18004a173  mov     [r9+8], r12
0x18004a177  jmp     short loc_18004A194
0x18004a179  xor     edx, edx; Val
0x18004a17b  mov     rcx, r9; void *
0x18004a17e  call    memset_0
0x18004a183  call    cs:__imp__o__errno
0x18004a189  mov     dword ptr [rax], 22h ; '"'
0x18004a18f  call    _invalid_parameter_noinfo
0x18004a194  add     cs:qword_180097D88, 10h
0x18004a19c  cmp     cs:byte_180097D78, 0
0x18004a1a3  jnz     loc_18004A26A
0x18004a1a9  mov     rcx, cs:pti
0x18004a1b0  test    rcx, rcx
0x18004a1b3  jnz     loc_18004A23A
0x18004a1b9  call    cs:__imp_GetLastError
0x18004a1bf  mov     esi, eax
0x18004a1c1  xor     r8d, r8d; pcbe
0x18004a1c4  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18004a1cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004a1d2  call    cs:__imp_CreateThreadpoolTimer
0x18004a1d8  mov     rbp, rax
0x18004a1db  mov     rdi, cs:pti
0x18004a1e2  test    rdi, rdi
0x18004a1e5  jz      short loc_18004A21F
0x18004a1e7  call    cs:__imp_GetLastError
0x18004a1ed  mov     ebx, eax
0x18004a1ef  xor     r9d, r9d; msWindowLength
0x18004a1f2  xor     r8d, r8d; msPeriod
0x18004a1f5  xor     edx, edx; pftDueTime
0x18004a1f7  mov     rcx, rdi; pti
0x18004a1fa  call    cs:__imp_SetThreadpoolTimer
0x18004a200  mov     edx, 1; fCancelPendingCallbacks
0x18004a205  mov     rcx, rdi; pti
0x18004a208  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004a20e  mov     rcx, rdi; pti
0x18004a211  call    cs:__imp_CloseThreadpoolTimer
0x18004a217  mov     ecx, ebx; dwErrCode
0x18004a219  call    cs:__imp_SetLastError
0x18004a21f  mov     cs:pti, rbp
0x18004a226  mov     ecx, esi; dwErrCode
0x18004a228  call    cs:__imp_SetLastError
0x18004a22e  mov     rcx, cs:pti; pti
0x18004a235  test    rcx, rcx
0x18004a238  jz      short loc_18004A26A
0x18004a23a  mov     rax, 0FFFFFFFF4D2FA200h
0x18004a244  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18004a24c  mov     r9d, 124F8h; msWindowLength
0x18004a252  xor     r8d, r8d; msPeriod
0x18004a255  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18004a25d  call    cs:__imp_SetThreadpoolTimer
0x18004a263  mov     cs:byte_180097D78, 1
0x18004a26a  mov     ebx, [rsp+0D8h+var_88]
0x18004a26e  mov     edi, [rsp+0D8h+var_84]
0x18004a272  mov     esi, [rsp+0D8h+var_80]
0x18004a276  lea     rcx, stru_180097D68; SRWLock
0x18004a27d  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a283  mov     ecx, [rsp+0D8h+var_7C]
0x18004a287  test    r13d, r13d
0x18004a28a  jz      short loc_18004A2B6
0x18004a28c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18004a293  test    rax, rax
0x18004a296  jnz     short loc_18004A2A4
0x18004a298  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18004a29f  test    rax, rax
0x18004a2a2  jz      short loc_18004A2B6
0x18004a2a4  mov     edx, ecx
0x18004a2a6  xor     r9d, r9d
0x18004a2a9  mov     r8d, r13d
0x18004a2ac  mov     ecx, 3B06A61h
0x18004a2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2b6  test    edi, edi
0x18004a2b8  jnz     short loc_18004A326
0x18004a2ba  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18004a2c0  test    eax, eax
0x18004a2c2  jz      short loc_18004A326
0x18004a2c4  lea     rcx, stru_180097D68; SRWLock
0x18004a2cb  call    cs:__imp_AcquireSRWLockExclusive
0x18004a2d1  cmp     cs:qword_180097DC8, 0
0x18004a2d9  jnz     short loc_18004A318
0x18004a2db  mov     cs:qword_180097DC8, 0
0x18004a2e6  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18004a2ed  test    rax, rax
0x18004a2f0  jnz     short loc_18004A2FE
0x18004a2f2  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18004a2f9  test    rax, rax
0x18004a2fc  jz      short loc_18004A318
0x18004a2fe  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18004a305  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18004a30c  lea     rcx, qword_180097DC8
0x18004a313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a318  lea     rcx, stru_180097D68; SRWLock
0x18004a31f  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a325  nop
0x18004a326  bt      r15d, 0Ah
0x18004a32b  jnb     short loc_18004A365
0x18004a32d  mov     eax, ebx
0x18004a32f  bts     eax, 1Fh
0x18004a333  mov     edx, ebx
0x18004a335  bt      r15d, 0Bh
0x18004a33a  cmovb   edx, eax
0x18004a33d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18004a344  test    rax, rax
0x18004a347  jnz     short loc_18004A355
0x18004a349  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18004a350  test    rax, rax
0x18004a353  jz      short loc_18004A365
0x18004a355  xor     r9d, r9d
0x18004a358  xor     r8d, r8d
0x18004a35b  mov     ecx, 3B06A61h
0x18004a360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a365  test    edi, edi
0x18004a367  jnz     short loc_18004A3C9
0x18004a369  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18004a370  test    rax, rax
0x18004a373  jz      short loc_18004A384
0x18004a375  mov     r8b, 2
0x18004a378  mov     edx, ebx
0x18004a37a  mov     ecx, 3B06A61h
0x18004a37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a384  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18004a38b  test    rax, rax
0x18004a38e  jz      short loc_18004A3C9
0x18004a390  mov     [rsp+0D8h+var_A0], 1
0x18004a399  mov     [rsp+0D8h+var_A8], 0
0x18004a39e  mov     [rsp+0D8h+var_B0], 0
0x18004a3a7  lea     rdx, [rsp+0D8h+var_50]
0x18004a3af  mov     [rsp+0D8h+var_B8], rdx
0x18004a3b4  mov     r9d, esi
0x18004a3b7  xor     r8d, r8d
0x18004a3ba  lea     rdx, [rsp+0D8h+var_60]
0x18004a3bf  mov     ecx, 3B06A61h
0x18004a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3c9  mov     rcx, [rsp+0D8h+var_48]
0x18004a3d1  xor     rcx, rsp; StackCookie
0x18004a3d4  call    __security_check_cookie
0x18004a3d9  mov     rbx, [rsp+0D8h+arg_10]
0x18004a3e1  add     rsp, 0A0h
0x18004a3e8  pop     r15
0x18004a3ea  pop     r14
0x18004a3ec  pop     r13
0x18004a3ee  pop     r12
0x18004a3f0  pop     rdi
0x18004a3f1  pop     rsi
0x18004a3f2  pop     rbp
0x18004a3f3  retn
```
