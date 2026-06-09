# I_s_RPC_SCardTransmit

- ea: `0x180015790`
- end: `0x180016723`
- name: `I_s_RPC_SCardTransmit`
- size: `3987`
- prototype: `__int64 __fastcall(__int64, int, const unsigned __int8 *const *, const unsigned __int8 *, unsigned int, unsigned int, void **, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007060`

## callees

- `0x18000139c`
- `0x1800013c8`
- `0x1800028b0`
- `0x18000d190`
- `0x18000f87c`
- `0x18000fcf0`
- `0x180010910`
- `0x1800125e0`
- `0x180012740`
- `0x1800136a0`
- `0x180015790`
- `0x180016d20`
- `0x180016f34`
- `0x180023168`
- `0x180023276`
- `0x1800263c4`
- `0x18002aec4`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800159f8`
- `msvcrt!memcpy_s` at `0x180015a7a`
- `msvcrt!memcpy_s` at `0x180015eaf`
- `msvcrt!memcpy_s` at `0x180015f3f`
- `msvcrt!memcpy_s` at `0x1800159f8`
- `msvcrt!memcpy_s` at `0x180015a7a`
- `msvcrt!memcpy_s` at `0x180015eaf`
- `msvcrt!memcpy_s` at `0x180015f3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015bba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015dca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016035`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015bba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015dca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016035`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015c0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015fe6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016085`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015c0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015fe6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016085`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ee3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001652b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ee3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001652b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016558`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016506`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001651d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001654a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016506`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001651d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001654a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001580c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015aa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001580c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015aa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800159d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015e8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800159d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015b16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015e8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015ae7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015b45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015fcb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015ae7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015b45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015fcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015afe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015afe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015af5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015af5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015abf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015f7f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015abf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800161ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800161ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800157ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015802`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800157ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180015802`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800161e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800161e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016246`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016211`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016211`
- `RPCRT4!RpcRevertToSelf` at `0x180016255`
- `RPCRT4!RpcRevertToSelf` at `0x1800165b2`
- `RPCRT4!RpcRevertToSelf` at `0x180016255`
- `RPCRT4!RpcRevertToSelf` at `0x1800165b2`
- `RPCRT4!RpcImpersonateClient` at `0x180016187`
- `RPCRT4!RpcImpersonateClient` at `0x180016187`

## pseudocode

```c
__int64 __fastcall I_s_RPC_SCardTransmit(
        __int64 a1,
        int a2,
        const unsigned __int8 *const *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6,
        void **a7,
        _QWORD *a8,
        unsigned int *a9)
{
  __int64 v10; // r14
  unsigned int v12; // edi
  __int64 v13; // rcx
  _DWORD *v14; // rax
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 v17; // rcx
  int v18; // r14d
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdx
  void *v21; // r10
  unsigned __int64 v22; // rbx
  DWORD v23; // r12d
  unsigned __int64 v24; // r15
  unsigned __int64 v25; // r8
  char *v26; // rax
  char *v27; // rbx
  signed __int64 v28; // r14
  void *v29; // r13
  HANDLE v30; // rax
  rsize_t v31; // rdx
  struct _TP_TIMER *v32; // rcx
  DWORD v33; // r15d
  struct _TP_TIMER *v34; // r12
  struct _TP_TIMER *v35; // r14
  DWORD v36; // ebx
  void (__fastcall *v37)(__int64, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v38)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v39; // rdx
  void (__fastcall *v40)(__int64, __int64, _QWORD, _QWORD); // rax
  unsigned int v41; // r15d
  DWORD LastError; // r14d
  unsigned __int8 v43; // al
  int v44; // eax
  _DWORD *v45; // rax
  __int64 v46; // r8
  unsigned int v47; // ecx
  __int64 v48; // rdx
  int v49; // ebx
  unsigned __int64 v50; // r8
  unsigned __int64 v51; // rdx
  void *v52; // r10
  unsigned __int64 v53; // rbx
  DWORD v54; // r15d
  unsigned __int64 v55; // r12
  unsigned __int64 v56; // r8
  char *v57; // rax
  char *v58; // rbx
  signed __int64 v59; // r15
  HANDLE ProcessHeap; // rax
  rsize_t v61; // rdx
  struct _TP_TIMER *v62; // rcx
  DWORD v63; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  void (__fastcall *v65)(__int64, __int64, _QWORD, _QWORD); // rax
  void (__fastcall *v66)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v67; // rdx
  void (__fastcall *v68)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v69; // rcx
  unsigned __int8 v70; // al
  int v71; // eax
  HANDLE CurrentThread; // rax
  unsigned int v73; // ebx
  const unsigned __int8 *const *v74; // r14
  int v75; // ebx
  unsigned int v76; // ecx
  CReaderProxy *v77; // r12
  unsigned int v78; // r8d
  unsigned int v79; // ebx
  const WCHAR *v80; // r14
  unsigned __int8 *v81; // r8
  unsigned __int8 *v82; // r15
  int v83; // r13d
  __int64 v84; // rcx
  const WCHAR *v85; // rax
  __int64 v86; // rax
  int v87; // r13d
  const WCHAR *v88; // rbx
  char *v89; // rsi
  _DWORD *v90; // rax
  void **v91; // r12
  _DWORD *v92; // rcx
  unsigned int v93; // eax
  unsigned __int64 v94; // rcx
  void *v95; // rcx
  unsigned int v96; // r13d
  unsigned int *v97; // r12
  void *v98; // rax
  __int64 v99; // rcx
  void **v100; // rsi
  void *v101; // rbx
  HANDLE v102; // rax
  void *v103; // rbx
  HANDLE v104; // rax
  _QWORD *v105; // rbx
  void *v106; // rsi
  HANDLE v107; // rax
  int v109; // ecx
  int v110; // r8d
  int v111; // r9d
  ulong v112; // ebx
  int v113; // [rsp+30h] [rbp-138h]
  int v114; // [rsp+50h] [rbp-118h]
  unsigned int v115; // [rsp+50h] [rbp-118h]
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp-110h] BYREF
  unsigned int v117; // [rsp+60h] [rbp-108h]
  int v118; // [rsp+64h] [rbp-104h]
  int v119; // [rsp+68h] [rbp-100h] BYREF
  __int16 v120; // [rsp+6Ch] [rbp-FCh]
  DWORD dwErrCode; // [rsp+70h] [rbp-F8h] BYREF
  unsigned __int8 v122[8]; // [rsp+78h] [rbp-F0h] BYREF
  void **v123; // [rsp+80h] [rbp-E8h] BYREF
  unsigned __int8 *v124; // [rsp+88h] [rbp-E0h]
  __int64 v125; // [rsp+90h] [rbp-D8h]
  ulong pExceptionObject; // [rsp+98h] [rbp-D0h] BYREF
  ulong v127; // [rsp+9Ch] [rbp-CCh] BYREF
  ulong v128; // [rsp+A0h] [rbp-C8h] BYREF
  ulong v129; // [rsp+A4h] [rbp-C4h] BYREF
  ulong v130; // [rsp+A8h] [rbp-C0h] BYREF
  ulong v131; // [rsp+ACh] [rbp-BCh] BYREF
  ulong v132; // [rsp+B0h] [rbp-B8h] BYREF
  ulong v133; // [rsp+B4h] [rbp-B4h] BYREF
  ulong v134; // [rsp+B8h] [rbp-B0h] BYREF
  ulong v135; // [rsp+BCh] [rbp-ACh] BYREF
  ulong v136; // [rsp+C0h] [rbp-A8h] BYREF
  ulong v137; // [rsp+C4h] [rbp-A4h] BYREF
  ulong v138; // [rsp+C8h] [rbp-A0h] BYREF
  struct _FILETIME Source[2]; // [rsp+D0h] [rbp-98h] BYREF
  const WCHAR *v140; // [rsp+E0h] [rbp-88h] BYREF
  void *Block; // [rsp+E8h] [rbp-80h]
  __int64 v142; // [rsp+F0h] [rbp-78h]
  __int64 v143; // [rsp+F8h] [rbp-70h]
  PSID SidToCheck; // [rsp+100h] [rbp-68h] BYREF
  __int64 *v145; // [rsp+108h] [rbp-60h]
  __int64 v146; // [rsp+110h] [rbp-58h]
  __int64 v147; // [rsp+118h] [rbp-50h] BYREF
  char v148[32]; // [rsp+120h] [rbp-48h] BYREF
  __int64 IsMember; // [rsp+170h] [rbp+8h] BYREF
  const unsigned __int8 *const *v150; // [rsp+180h] [rbp+18h]

  v150 = a3;
  v10 = a2;
  v12 = 0;
  v123 = &CBuffer::`vftable';
  v124 = 0;
  v125 = 0;
  v140 = (const WCHAR *)&CBuffer::`vftable';
  Block = 0;
  v142 = 0;
  if ( !TlsSetValue(dwTlsIndex, *(LPVOID *)(a1 + 72)) || !TlsSetValue(dword_18004B240, *(LPVOID *)a1) )
    GetLastError();
  try
  {
    _InterlockedExchange(&g_fExtendShutdownTimer, 1);
    *(_QWORD *)v122 = 0;
    CMutex::Grab((CMutex *)(a1 + 80));
    v147 = a1;
    if ( *(_DWORD *)(a1 + 60) <= (unsigned int)v10
      || (_mm_lfence(), (v143 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8 * v10)) == 0) )
    {
      v137 = -2146435055;
      throw &v137;
    }
    v114 = *(_DWORD *)Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc__descriptor;
    if ( (*(_DWORD *)Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc__descriptor & 4) == 0 )
    {
      IsMember = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc>::GetCachedFeatureEnabledState(
                              v13,
                              &IsMember);
      LOWORD(v114) = IsMember;
    }
    v119 = 0;
    v120 = 3;
    dwErrCode = 3;
    v14 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(&SidToCheck, &qword_18004C230, 2);
    v16 = v14[1];
    LODWORD(IsMember) = v16;
    v17 = (unsigned int)v14[2];
    v117 = v14[2];
    v18 = v14[4];
    v118 = v18;
    if ( !*v14 )
    {
LABEL_38:
      if ( v16 )
      {
        v37 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
        if ( g_wil_details_internalRecordFeatureUsage
          || (v37 = (void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
        {
          v37(44669353, (unsigned int)v17, v16, 0);
        }
      }
      if ( !v18 && wil::details::g_enabledStateManager )
      {
        AcquireSRWLockExclusive(&SRWLock);
        if ( !qword_18004B328 )
        {
          qword_18004B328 = 0;
          v38 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
          if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
            || (v38 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
          {
            v38(&qword_18004B328, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
          }
        }
        ReleaseSRWLockExclusive(&SRWLock);
      }
      if ( (v114 & 0x400) != 0 )
      {
        v39 = 2;
        v17 = 2147483650LL;
        if ( (v114 & 0x800) != 0 )
          v39 = 2147483650LL;
        v40 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
        if ( g_wil_details_internalRecordFeatureUsage
          || (v40 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
        {
          v40(44669353, v39, 0, 0);
        }
      }
      if ( !v18 )
      {
        if ( g_wil_details_realtimeFeatureUsageHook )
        {
          LOBYTE(v15) = 3;
          g_wil_details_realtimeFeatureUsageHook(44669353, 2, v15);
        }
        if ( g_wil_details_pfnFeatureLoggingHook )
          g_wil_details_pfnFeatureLoggingHook(44669353, &v119, 0, 1, &dwErrCode, 0, 0, 1);
      }
      if ( a4 && (v41 = a5, a5 >= 0xA) && a4[1] == 0xA4 )
      {
        v17 = 0;
        LastError = 5;
        while ( 1 )
        {
          v43 = a4[v17++ + 5];
          if ( v43 != *((_BYTE *)&qword_18004B238 + v17 - 1) )
            break;
          if ( v17 == 5 )
          {
            v44 = 0;
            goto LABEL_68;
          }
        }
        v44 = v43 < *((_BYTE *)&qword_18004B238 + v17 - 1) ? -1 : 1;
LABEL_68:
        if ( !v44 )
          goto LABEL_132;
      }
      else
      {
        LastError = 5;
      }
      v118 = *(_DWORD *)Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc__descriptor;
      if ( (v118 & 4) == 0 )
      {
        IsMember = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc>::GetCachedFeatureEnabledState(
                                v17,
                                &IsMember);
        v118 = IsMember;
      }
      pftDueTime.dwLowDateTime = 0;
      LOWORD(pftDueTime.dwHighDateTime) = 3;
      v119 = 3;
      v45 = (_DWORD *)wil_details_FeatureReporting_RecordUsageInCache(v148, &qword_18004C230, 2);
      v47 = v45[1];
      v115 = v47;
      v48 = (unsigned int)v45[2];
      v117 = v45[2];
      v49 = v45[4];
      LODWORD(IsMember) = v49;
      if ( !*v45 || !wil::details::g_enabledStateManager || wil::details::g_processShutdownInProgress )
      {
LABEL_101:
        if ( v47 )
        {
          v65 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
          if ( g_wil_details_internalRecordFeatureUsage
            || (v65 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
          {
            v65(44669353, v48, v47, 0);
          }
        }
        if ( !v49 && wil::details::g_enabledStateManager )
        {
          AcquireSRWLockExclusive(&SRWLock);
          if ( !qword_18004B328 )
          {
            qword_18004B328 = 0;
            v66 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
            if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
              || (v66 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
            {
              v66(&qword_18004B328, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
            }
          }
          ReleaseSRWLockExclusive(&SRWLock);
        }
        if ( (v118 & 0x400) != 0 )
        {
          v67 = 2;
          if ( (v118 & 0x800) != 0 )
            v67 = 2147483650LL;
          v68 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
          if ( g_wil_details_internalRecordFeatureUsage
            || (v68 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
          {
            v68(44669353, v67, 0, 0);
          }
        }
        if ( !v49 )
        {
          if ( g_wil_details_realtimeFeatureUsageHook )
          {
            LOBYTE(v46) = 3;
            g_wil_details_realtimeFeatureUsageHook(44669353, 2, v46);
          }
          if ( g_wil_details_pfnFeatureLoggingHook )
          {
            LOBYTE(v113) = 0;
            g_wil_details_pfnFeatureLoggingHook(44669353, &pftDueTime, 0, 1, &v119, 0, v113, 1);
          }
        }
        v41 = a5;
        if ( !a4 || a5 < 0xC || a4[1] != 0xA4 )
          goto LABEL_146;
        v69 = 0;
        while ( 1 )
        {
          v70 = a4[v69++ + 7];
          if ( v70 != *((_BYTE *)&qword_18004B238 + v69 - 1) )
            break;
          if ( v69 == 5 )
          {
            v71 = 0;
            goto LABEL_131;
          }
        }
        v71 = v70 < *((_BYTE *)&qword_18004B238 + v69 - 1) ? -1 : 1;
LABEL_131:
        if ( v71 )
          goto LABEL_146;
LABEL_132:
        if ( !RpcImpersonateClient(0) )
        {
          pftDueTime = 0;
          if ( qword_18004BFA0 )
          {
            SidToCheck = (PSID)*((_QWORD *)qword_18004BFA0 + 3);
            v145 = (__int64 *)*((_QWORD *)qword_18004BFA0 + 1);
            v146 = *((_QWORD *)qword_18004BFA0 + 2);
            CurrentThread = GetCurrentThread();
            if ( OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)&pftDueTime) )
            {
              v73 = 0;
              while ( 1 )
              {
                LODWORD(IsMember) = 0;
                if ( !CheckTokenMembership(*(HANDLE *)&pftDueTime, *(&SidToCheck + v73), (PBOOL)&IsMember) )
                  break;
                if ( (_DWORD)IsMember )
                {
                  LastError = 0;
                  goto LABEL_142;
                }
                if ( ++v73 >= 3 )
                  goto LABEL_142;
              }
            }
            LastError = GetLastError();
LABEL_142:
            if ( pftDueTime )
              CloseHandle(*(HANDLE *)&pftDueTime);
            if ( !LastError )
            {
              RpcRevertToSelf();
LABEL_146:
              v74 = v150;
              *(_DWORD *)&v122[4] = *((_DWORD *)v150 + 4) + 8;
              v75 = *(_DWORD *)v150;
              *(_DWORD *)v122 = *(_DWORD *)v150;
              CBuffer::Presize((CBuffer *)&v123, *(_DWORD *)&v122[4] + v41, 0);
              v76 = *a9;
              if ( *a9 <= g_dwDefaultIOMax )
              {
                CBuffer::Presize((CBuffer *)&v140, a6 + g_dwDefaultIOMax, 0);
              }
              else
              {
                if ( v76 + a6 < a6 )
                {
                  v127 = -2147024362;
                  throw &v127;
                }
                CBuffer::Presize((CBuffer *)&v140, v76 + a6, 0);
              }
              v77 = *(CReaderProxy **)v143;
              if ( !v75 )
                *(_DWORD *)v122 = CReaderProxy::Protocol(*(CReaderProxy **)v143);
              CBuffer::Set((CBuffer *)&v123, v122, 8u);
              v78 = *((_DWORD *)v74 + 4);
              if ( v78 )
                CBuffer::Append((CBuffer *)&v123, v74[1], v78);
              CBuffer::Append((CBuffer *)&v123, a4, v41);
              try
              {
                v79 = v125;
                v80 = &Data;
                v81 = (unsigned __int8 *)&Data;
                v82 = v124;
                v83 = HIDWORD(v125);
                if ( HIDWORD(v125) )
                  v81 = v124;
                CReaderProxy::ReaderTransmit(v77, (struct CReader::ActiveState *)(v143 + 8), v81, v125, &v140);
                v84 = v79;
                v85 = &Data;
                if ( v83 )
                  v85 = (const WCHAR *)v82;
                if ( v79 )
                {
                  do
                  {
                    *(_BYTE *)v85 = 0;
                    v85 = (const WCHAR *)((char *)v85 + 1);
                    --v84;
                  }
                  while ( v84 );
                }
                v86 = a5;
                if ( a5 )
                {
                  do
                  {
                    *a4++ = 0;
                    --v86;
                  }
                  while ( v86 );
                }
              }
              catch ( ulong v134 )
              {
                WppTraceIndent(v84, 2);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
                {
                  v112 = v134;
                }
                else
                {
                  v112 = v134;
                  WPP_SF_sD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    27,
                    (unsigned int)WPP_8fae02f726263adb5326c29facded416_Traceguids,
                    (_DWORD)WPP_pszIndent,
                    v134);
                }
                if ( v112 == 121 )
                  v112 = -2146435025;
                v135 = v112;
                throw &v135;
              }
              catch ( ... )
              {
                WppTraceIndent(v84, 2);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    28,
                    WPP_8fae02f726263adb5326c29facded416_Traceguids,
                    WPP_pszIndent);
                }
                v136 = -2146435052;
                throw &v136;
              }
              v87 = v142;
              if ( (unsigned int)v142 < 8 )
              {
                v128 = -2146435071;
                throw &v128;
              }
              v88 = &Data;
              v89 = (char *)Block;
              LODWORD(IsMember) = HIDWORD(v142);
              if ( HIDWORD(v142) )
                v88 = (const WCHAR *)Block;
              if ( (unsigned int)v142 < *((_DWORD *)v88 + 1) )
              {
                v129 = -2146435071;
                throw &v129;
              }
              v90 = AllocH(0x18u);
              v91 = a7;
              *a7 = v90;
              if ( !v90 )
              {
                v130 = -2146435066;
                throw &v130;
              }
              *v90 = *(_DWORD *)v88;
              *((_QWORD *)*v91 + 1) = 0;
              v92 = *v91;
              v93 = *((_DWORD *)v88 + 1);
              if ( v93 < 8 )
              {
                v92[4] = -1;
                v133 = 534;
                throw &v133;
              }
              v92[4] = v93 - 8;
              v94 = *((unsigned int *)*v91 + 4);
              if ( (_DWORD)v94 )
              {
                *((_QWORD *)*v91 + 1) = AllocH(v94);
                v95 = (void *)*((_QWORD *)*v91 + 1);
                if ( !v95 )
                {
                  v131 = -2146435066;
                  throw &v131;
                }
                memcpy_0(v95, v88 + 4, *((unsigned int *)*v91 + 4));
              }
              v96 = v87 - *((_DWORD *)v88 + 1);
              v97 = a9;
              *a9 = v96;
              v98 = AllocH(v96);
              *a8 = v98;
              if ( !v98 )
              {
                v132 = -2146435066;
                throw &v132;
              }
              v99 = *((unsigned int *)v88 + 1);
              if ( (unsigned int)IsMember > (unsigned int)v99 )
                v80 = (const WCHAR *)&v89[v99];
              memcpy_0(v98, v80, *v97);
              CServiceThreadLock::~CServiceThreadLock((CServiceThreadLock *)&v147);
              goto LABEL_218;
            }
          }
          RpcRevertToSelf();
        }
        if ( (unsigned int)dword_18004B048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004B048, 0x400000000000LL) )
        {
          IsMember = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v109,
            (unsigned int)word_180042A82,
            v110,
            v111,
            (__int64)&IsMember);
        }
        pExceptionObject = -2146435033;
        throw &pExceptionObject;
      }
      if ( wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      {
LABEL_100:
        v48 = v117;
        v47 = v115;
        goto LABEL_101;
      }
      AcquireSRWLockExclusive(&SRWLock);
      if ( !wil::details::g_enabledStateManager
        || wil::details::g_processShutdownInProgress
        || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
      {
LABEL_99:
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_100;
      }
      SidToCheck = (PSID)44669353;
      v145 = &qword_18004C230;
      v50 = qword_18004B2F0;
      v51 = qword_18004B2F0 - (_QWORD)::Source;
      v52 = Destination;
      if ( (_BYTE *)Destination - (_BYTE *)::Source + 16 >= (unsigned __int64)(qword_18004B2F0 - (_QWORD)::Source) )
      {
        v53 = 16;
        if ( 2 * v51 > 0x10 )
          v53 = 2 * v51;
        if ( v51 < v53 )
        {
          v54 = GetLastError();
          dwErrCode = v54;
          v55 = (v53 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
          v57 = (char *)wil::details::ProcessHeapAlloc(0, v55, v56);
          v58 = v57;
          if ( !v57 )
          {
            SetLastError(v54);
LABEL_94:
            if ( !byte_18004B2D8 )
            {
              v62 = pti;
              if ( pti
                || (v63 = GetLastError(),
                    ThreadpoolTimer = CreateThreadpoolTimer(
                                        _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                        &wil::details::g_enabledStateManager,
                                        0),
                    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                      &pti,
                      ThreadpoolTimer),
                    SetLastError(v63),
                    (v62 = pti) != 0) )
              {
                Source[0] = (struct _FILETIME)-3000000000LL;
                SetThreadpoolTimer(v62, Source, 0, 0x124F8u);
                byte_18004B2D8 = 1;
              }
            }
            v49 = IsMember;
            goto LABEL_99;
          }
          v59 = (_BYTE *)Destination - (_BYTE *)::Source;
          memcpy_s(v57, v55, ::Source, (_BYTE *)Destination - (_BYTE *)::Source);
          Source[0] = (struct _FILETIME)lpMem;
          lpMem = v58;
          if ( Source[0] )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, *(LPVOID *)Source);
          }
          ::Source = v58;
          Destination = &v58[v59];
          qword_18004B2F0 = (__int64)&v58[v55];
          SetLastError(dwErrCode);
          v50 = qword_18004B2F0;
          v52 = Destination;
        }
      }
      v61 = 0;
      if ( (unsigned __int64)v52 < v50 )
        v61 = v50 - (_QWORD)v52;
      memcpy_s(v52, v61, &SidToCheck, 0x10u);
      Destination = (char *)Destination + 16;
      goto LABEL_94;
    }
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_37:
      v17 = v117;
      goto LABEL_38;
    }
    AcquireSRWLockExclusive(&SRWLock);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_36:
      ReleaseSRWLockExclusive(&SRWLock);
      v18 = v118;
      goto LABEL_37;
    }
    Source[0] = (struct _FILETIME)44669353LL;
    Source[1] = (struct _FILETIME)&qword_18004C230;
    v19 = qword_18004B2F0;
    v20 = qword_18004B2F0 - (_QWORD)::Source;
    v21 = Destination;
    if ( (_BYTE *)Destination - (_BYTE *)::Source + 16 >= (unsigned __int64)(qword_18004B2F0 - (_QWORD)::Source) )
    {
      v22 = 16;
      if ( 2 * v20 > 0x10 )
        v22 = 2 * v20;
      if ( v20 < v22 )
      {
        v23 = GetLastError();
        v24 = (v22 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v26 = (char *)wil::details::ProcessHeapAlloc(0, v24, v25);
        v27 = v26;
        if ( !v26 )
        {
          SetLastError(v23);
LABEL_29:
          if ( !byte_18004B2D8 )
          {
            v32 = pti;
            if ( pti )
              goto LABEL_34;
            v33 = GetLastError();
            v34 = CreateThreadpoolTimer(
                    _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                    &wil::details::g_enabledStateManager,
                    0);
            v35 = pti;
            if ( pti )
            {
              v36 = GetLastError();
              SetThreadpoolTimer(v35, 0, 0, 0);
              WaitForThreadpoolTimerCallbacks(v35, 1);
              CloseThreadpoolTimer(v35);
              SetLastError(v36);
            }
            pti = v34;
            SetLastError(v33);
            v32 = pti;
            if ( pti )
            {
LABEL_34:
              pftDueTime = (struct _FILETIME)-3000000000LL;
              SetThreadpoolTimer(v32, &pftDueTime, 0, 0x124F8u);
              byte_18004B2D8 = 1;
            }
          }
          v16 = IsMember;
          goto LABEL_36;
        }
        v28 = (_BYTE *)Destination - (_BYTE *)::Source;
        memcpy_s(v26, v24, ::Source, (_BYTE *)Destination - (_BYTE *)::Source);
        v29 = lpMem;
        lpMem = v27;
        if ( v29 )
        {
          v30 = GetProcessHeap();
          HeapFree(v30, 0, v29);
        }
        ::Source = v27;
        Destination = &v27[v28];
        qword_18004B2F0 = (__int64)&v27[v24];
        SetLastError(v23);
        v19 = qword_18004B2F0;
        v21 = Destination;
      }
    }
    v31 = 0;
    if ( (unsigned __int64)v21 < v19 )
      v31 = v19 - (_QWORD)v21;
    memcpy_s(v21, v31, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_29;
  }
  catch ( ulong v138 )
  {
    LODWORD(IsMember) = v138;
    if ( v138 )
    {
LABEL_178:
      v100 = a7;
      if ( *a7 )
      {
        v101 = (void *)*((_QWORD *)*a7 + 1);
        if ( v101 )
        {
          v102 = GetProcessHeap();
          HeapFree(v102, 0, v101);
        }
        v103 = *v100;
        v104 = GetProcessHeap();
        HeapFree(v104, 0, v103);
        *v100 = 0;
      }
      v105 = a8;
      v106 = (void *)*a8;
      if ( *a8 )
      {
        v107 = GetProcessHeap();
        HeapFree(v107, 0, v106);
        *v105 = 0;
      }
    }
    v89 = (char *)Block;
    v82 = v124;
    v12 = IsMember;
  }
  catch ( ... )
  {
    LODWORD(IsMember) = -2146435055;
    goto LABEL_178;
  }
LABEL_218:
  if ( v89 )
    operator delete[](v89);
  if ( v82 )
    operator delete[](v82);
  return v12;
}

```

## disassembly

```asm
0x180015790  mov     r11, rsp
0x180015793  mov     [r11+10h], rbx
0x180015797  mov     [r11+20h], rsi
0x18001579b  mov     [r11+18h], r8
0x18001579f  push    rdi
0x1800157a0  push    r12
0x1800157a2  push    r13
0x1800157a4  push    r14
0x1800157a6  push    r15
0x1800157a8  sub     rsp, 140h
0x1800157af  mov     rsi, r9
0x1800157b2  movsxd  r14, edx
0x1800157b5  mov     rbx, rcx
0x1800157b8  xor     edi, edi
0x1800157ba  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800157c1  mov     [r11-0E8h], rax
0x1800157c8  mov     [r11-0E0h], rdi
0x1800157cf  mov     [r11-0D8h], rdi
0x1800157d6  mov     [r11-88h], rax
0x1800157dd  mov     [r11-80h], rdi
0x1800157e1  mov     [r11-78h], rdi
0x1800157e5  mov     rdx, [rcx+48h]; lpTlsValue
0x1800157e9  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800157ef  call    cs:__imp_TlsSetValue
0x1800157f5  test    eax, eax
0x1800157f7  jz      short loc_18001580C
0x1800157f9  mov     rdx, [rbx]; lpTlsValue
0x1800157fc  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x180015802  call    cs:__imp_TlsSetValue
0x180015808  test    eax, eax
0x18001580a  jnz     short loc_180015812
0x18001580c  call    cs:__imp_GetLastError
0x180015812  mov     eax, 1
0x180015817  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x18001581d  mov     qword ptr [rsp+168h+var_F0], rdi
0x180015822  lea     rcx, [rbx+50h]; this
0x180015826  call    ?Grab@CMutex@@QEAAXXZ; CMutex::Grab(void)
0x18001582b  mov     [rsp+168h+var_50], rbx
0x180015833  cmp     [rbx+3Ch], r14d
0x180015837  jbe     loc_180016702
0x18001583d  lfence
0x180015840  mov     rax, [rbx+40h]
0x180015844  mov     rax, [rax+r14*8]
0x180015848  mov     [rsp+168h+var_70], rax
0x180015850  test    rax, rax
0x180015853  jz      loc_180016702
0x180015859  mov     rax, cs:Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc__descriptor
0x180015860  mov     ebx, [rax]
0x180015862  mov     [rsp+168h+var_118], ebx
0x180015866  test    bl, 4
0x180015869  jnz     short loc_180015889
0x18001586b  lea     rdx, [rsp+168h+IsMember]
0x180015873  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockFidoAppletSelectionViaWinSCardIgnoreLc>::GetCachedFeatureEnabledState(void)
0x180015878  mov     rcx, [rax]
0x18001587b  mov     [rsp+168h+IsMember], rcx
0x180015883  mov     eax, ecx
0x180015885  mov     [rsp+168h+var_118], ecx
0x180015889  mov     [rsp+168h+var_100], edi
0x18001588d  mov     [rsp+168h+var_FC], 3
0x180015894  mov     [rsp+168h+dwErrCode], 3
0x18001589c  mov     r8d, 2
0x1800158a2  lea     r12, qword_18004C230
0x1800158a9  mov     rdx, r12
0x1800158ac  lea     rcx, [rsp+168h+SidToCheck]
0x1800158b4  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800158b9  mov     ebx, [rax+4]
0x1800158bc  mov     dword ptr [rsp+168h+IsMember], ebx
0x1800158c3  mov     ecx, [rax+8]
0x1800158c6  mov     [rsp+168h+var_108], ecx
0x1800158ca  mov     r14d, [rax+10h]
0x1800158ce  mov     [rsp+168h+var_104], r14d
0x1800158d3  cmp     dword ptr [rax], 0
0x1800158d6  jz      loc_180015B76
0x1800158dc  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800158e2  test    eax, eax
0x1800158e4  jz      loc_180015B72
0x1800158ea  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800158f1  jnz     loc_180015B72
0x1800158f7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800158fe  test    rax, rax
0x180015901  jz      short loc_180015910
0x180015903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015908  test    al, al
0x18001590a  jnz     loc_180015B72
0x180015910  lea     rcx, SRWLock; SRWLock
0x180015917  call    cs:__imp_AcquireSRWLockExclusive
0x18001591d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015923  test    eax, eax
0x180015925  jz      loc_180015B60
0x18001592b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180015932  jnz     loc_180015B60
0x180015938  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001593f  test    rax, rax
0x180015942  jz      short loc_180015951
0x180015944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015949  test    al, al
0x18001594b  jnz     loc_180015B60
0x180015951  mov     [rsp+168h+Source], 2A999A9h
0x18001595d  mov     [rsp+168h+var_90], r12
0x180015965  mov     r8, cs:qword_18004B2F0
0x18001596c  mov     rdx, r8
0x18001596f  sub     rdx, cs:Source
0x180015976  mov     r10, cs:Destination
0x18001597d  mov     rax, r10
0x180015980  sub     rax, cs:Source
0x180015987  add     rax, 10h
0x18001598b  cmp     rax, rdx
0x18001598e  jb      loc_180015A59
0x180015994  lea     rax, [rdx+rdx]
0x180015998  mov     ebx, 10h
0x18001599d  cmp     rax, rbx
0x1800159a0  cmova   rbx, rax
0x1800159a4  cmp     rdx, rbx
0x1800159a7  jnb     loc_180015A59
0x1800159ad  call    cs:__imp_GetLastError
0x1800159b3  mov     r12d, eax
0x1800159b6  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800159ba  lea     r15, [rbx+40h]
0x1800159be  mov     rdx, r15; dwBytes
0x1800159c1  xor     ecx, ecx; dwFlags
0x1800159c3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800159c8  mov     rbx, rax
0x1800159cb  test    rax, rax
0x1800159ce  jnz     short loc_1800159DE
0x1800159d0  mov     ecx, r12d; dwErrCode
0x1800159d3  call    cs:__imp_SetLastError
0x1800159d9  jmp     loc_180015A88
0x1800159de  mov     r8, cs:Source; Source
0x1800159e5  mov     r14, cs:Destination
0x1800159ec  sub     r14, r8
0x1800159ef  mov     r9, r14; SourceSize
0x1800159f2  mov     rdx, r15; DestinationSize
0x1800159f5  mov     rcx, rbx; Destination
0x1800159f8  call    cs:__imp_memcpy_s
0x1800159fe  mov     r13, cs:lpMem
0x180015a05  mov     cs:lpMem, rbx
0x180015a0c  test    r13, r13
0x180015a0f  jz      short loc_180015A25
0x180015a11  call    cs:__imp_GetProcessHeap
0x180015a17  mov     rcx, rax; hHeap
0x180015a1a  mov     r8, r13; lpMem
0x180015a1d  xor     edx, edx; dwFlags
0x180015a1f  call    cs:__imp_HeapFree
0x180015a25  mov     cs:Source, rbx
0x180015a2c  lea     rax, [rbx+r14]
0x180015a30  mov     cs:Destination, rax
0x180015a37  lea     rax, [rbx+r15]
0x180015a3b  mov     cs:qword_18004B2F0, rax
0x180015a42  mov     ecx, r12d; dwErrCode
0x180015a45  call    cs:__imp_SetLastError
0x180015a4b  mov     r8, cs:qword_18004B2F0
0x180015a52  mov     r10, cs:Destination
0x180015a59  mov     rax, r8
0x180015a5c  sub     rax, r10
0x180015a5f  mov     rdx, rdi
0x180015a62  cmp     r10, r8
0x180015a65  cmovb   rdx, rax; DestinationSize
0x180015a69  mov     r9d, 10h; SourceSize
0x180015a6f  lea     r8, [rsp+168h+Source]; Source
0x180015a77  mov     rcx, r10; Destination
0x180015a7a  call    cs:__imp_memcpy_s
0x180015a80  add     cs:Destination, 10h
0x180015a88  cmp     cs:byte_18004B2D8, 0
0x180015a8f  jnz     loc_180015B52
0x180015a95  mov     rcx, cs:pti
0x180015a9c  test    rcx, rcx
0x180015a9f  jnz     loc_180015B28
0x180015aa5  call    cs:__imp_GetLastError
0x180015aab  mov     r15d, eax
0x180015aae  xor     r8d, r8d; pcbe
0x180015ab1  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180015ab8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015abf  call    cs:__imp_CreateThreadpoolTimer
0x180015ac5  mov     r12, rax
0x180015ac8  mov     r14, cs:pti
0x180015acf  test    r14, r14
0x180015ad2  jz      short loc_180015B0C
0x180015ad4  call    cs:__imp_GetLastError
0x180015ada  mov     ebx, eax
0x180015adc  xor     r9d, r9d; msWindowLength
0x180015adf  xor     r8d, r8d; msPeriod
0x180015ae2  xor     edx, edx; pftDueTime
0x180015ae4  mov     rcx, r14; pti
0x180015ae7  call    cs:__imp_SetThreadpoolTimer
0x180015aed  mov     edx, 1; fCancelPendingCallbacks
0x180015af2  mov     rcx, r14; pti
0x180015af5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015afb  mov     rcx, r14; pti
0x180015afe  call    cs:__imp_CloseThreadpoolTimer
0x180015b04  mov     ecx, ebx; dwErrCode
0x180015b06  call    cs:__imp_SetLastError
0x180015b0c  mov     cs:pti, r12
0x180015b13  mov     ecx, r15d; dwErrCode
0x180015b16  call    cs:__imp_SetLastError
0x180015b1c  mov     rcx, cs:pti; pti
0x180015b23  test    rcx, rcx
0x180015b26  jz      short loc_180015B52
0x180015b28  mov     r14, 0FFFFFFFF4D2FA200h
0x180015b32  mov     qword ptr [rsp+168h+pftDueTime.dwLowDateTime], r14
0x180015b37  mov     r9d, 124F8h; msWindowLength
0x180015b3d  xor     r8d, r8d; msPeriod
0x180015b40  lea     rdx, [rsp+168h+pftDueTime]; pftDueTime
0x180015b45  call    cs:__imp_SetThreadpoolTimer
0x180015b4b  mov     cs:byte_18004B2D8, 1
0x180015b52  mov     ebx, dword ptr [rsp+168h+IsMember]
0x180015b59  lea     r12, qword_18004C230
0x180015b60  lea     rcx, SRWLock; SRWLock
0x180015b67  call    cs:__imp_ReleaseSRWLockExclusive
0x180015b6d  mov     r14d, [rsp+168h+var_104]
0x180015b72  mov     ecx, [rsp+168h+var_108]
0x180015b76  test    ebx, ebx
0x180015b78  jz      short loc_180015BA4
0x180015b7a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015b81  test    rax, rax
0x180015b84  jnz     short loc_180015B92
0x180015b86  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015b8d  test    rax, rax
0x180015b90  jz      short loc_180015BA4
0x180015b92  mov     edx, ecx
0x180015b94  xor     r9d, r9d
0x180015b97  mov     r8d, ebx
0x180015b9a  mov     ecx, 2A999A9h
0x180015b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ba4  test    r14d, r14d
0x180015ba7  jnz     short loc_180015C11
0x180015ba9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015baf  test    eax, eax
0x180015bb1  jz      short loc_180015C11
0x180015bb3  lea     rcx, SRWLock; SRWLock
0x180015bba  call    cs:__imp_AcquireSRWLockExclusive
0x180015bc0  cmp     cs:qword_18004B328, 0
0x180015bc8  jnz     short loc_180015C03
0x180015bca  mov     cs:qword_18004B328, rdi
0x180015bd1  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180015bd8  test    rax, rax
0x180015bdb  jnz     short loc_180015BE9
0x180015bdd  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180015be4  test    rax, rax
0x180015be7  jz      short loc_180015C03
0x180015be9  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180015bf0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x180015bf7  lea     rcx, qword_18004B328
0x180015bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c03  lea     rcx, SRWLock; SRWLock
0x180015c0a  call    cs:__imp_ReleaseSRWLockExclusive
0x180015c10  nop
0x180015c11  mov     eax, [rsp+168h+var_118]
0x180015c15  bt      eax, 0Ah
0x180015c19  jnb     short loc_180015C54
0x180015c1b  bt      eax, 0Bh
0x180015c1f  mov     edx, 2
0x180015c24  mov     ecx, 80000002h
0x180015c29  cmovb   edx, ecx
0x180015c2c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180015c33  test    rax, rax
0x180015c36  jnz     short loc_180015C44
0x180015c38  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180015c3f  test    rax, rax
0x180015c42  jz      short loc_180015C54
0x180015c44  xor     r9d, r9d
0x180015c47  xor     r8d, r8d
0x180015c4a  mov     ecx, 2A999A9h
0x180015c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c54  test    r14d, r14d
0x180015c57  jnz     short loc_180015CB8
0x180015c59  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180015c60  test    rax, rax
0x180015c63  jz      short loc_180015C77
0x180015c65  mov     r8b, 3
0x180015c68  mov     edx, 2
0x180015c6d  mov     ecx, 2A999A9h
0x180015c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c77  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180015c7e  test    rax, rax
0x180015c81  jz      short loc_180015CB8
0x180015c83  mov     [rsp+168h+var_130], 1
0x180015c8c  mov     [rsp+168h+var_138], 0
0x180015c91  mov     [rsp+168h+var_140], rdi
0x180015c96  lea     rcx, [rsp+168h+dwErrCode]
0x180015c9b  mov     [rsp+168h+var_148], rcx
0x180015ca0  mov     r9d, 1
0x180015ca6  xor     r8d, r8d
0x180015ca9  lea     rdx, [rsp+168h+var_100]
0x180015cae  mov     ecx, 2A999A9h
0x180015cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb8  test    rsi, rsi
0x180015cbb  jz      short loc_180015D08
0x180015cbd  mov     r15d, [rsp+168h+arg_20]
0x180015cc5  cmp     r15d, 0Ah
0x180015cc9  jb      short loc_180015D08
0x180015ccb  cmp     byte ptr [rsi+1], 0A4h
0x180015ccf  jnz     short loc_180015D08
0x180015cd1  mov     rcx, rdi
0x180015cd4  lea     r13, qword_18004B238
0x180015cdb  mov     r14d, 5
0x180015ce1  movzx   eax, byte ptr [rsi+rcx+5]
0x180015ce6  inc     rcx
0x180015ce9  cmp     al, [rcx+r13-1]
0x180015cee  jnz     short loc_180015CF9
0x180015cf0  cmp     rcx, r14
  ... truncated ...
```
