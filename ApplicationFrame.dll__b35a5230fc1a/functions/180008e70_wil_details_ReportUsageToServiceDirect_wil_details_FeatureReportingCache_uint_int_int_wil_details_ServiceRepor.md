# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x180008e70`
- end: `0x1800092d5`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `1125`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180004e8c`
- `0x180007100`
- `0x180007b30`
- `0x180007c10`
- `0x180008370`
- `0x180008ce0`
- `0x180008d90`
- `0x18000caf0`
- `0x180035640`
- `0x180036270`

## callees

- `0x180008e70`
- `0x180035770`
- `0x180041100`
- `0x18004464a`
- `0x1800446fc`
- `0x18004c318`
- `0x180072010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000908c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000908c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000924e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000924e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009023`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009023`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009031`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000911b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000911b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fe6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000914d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000915c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008fe6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000914d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000915c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009145`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009145`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000912e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000918b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000912e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000918b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009106`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009106`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000913c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000913c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        __int64 a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int v8; // r15d
  int *v11; // rax
  int v12; // ebx
  unsigned int v13; // edi
  unsigned int v14; // r14d
  int v15; // ebp
  __int64 v16; // rcx
  DWORD dwLowDateTime; // r11d
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // rdx
  unsigned int *v20; // r9
  unsigned __int64 v21; // rbx
  DWORD LastError; // edi
  unsigned __int64 v23; // r14
  unsigned __int64 v24; // r8
  char *v25; // rax
  char *v26; // rbx
  signed __int64 v27; // r15
  void *v28; // rbp
  HANDLE ProcessHeap; // rax
  size_t v30; // r8
  struct _TP_TIMER *v31; // rcx
  DWORD v32; // ebp
  struct _TP_TIMER *ThreadpoolTimer; // r14
  struct _TP_TIMER *v34; // rdi
  DWORD v35; // ebx
  void (__fastcall *v36)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v37)(__int64 *, __int64 (__fastcall *)(void *), __int64); // rax
  __int64 v38; // rdx
  void (__fastcall *v39)(_QWORD, __int64, _QWORD, _QWORD); // rax
  int v41; // [rsp+30h] [rbp-68h]
  _FILETIME pftDueTime; // [rsp+38h] [rbp-60h] BYREF
  char v43[88]; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v46; // [rsp+C8h] [rbp+30h]
  unsigned int v47; // [rsp+D0h] [rbp+38h]

  v8 = a3;
  v11 = (int *)wil_details_FeatureReporting_RecordUsageInCache(v43, a1, a5);
  v12 = *v11;
  v13 = v11[1];
  v46 = v13;
  v14 = v11[2];
  v47 = v14;
  v15 = v11[4];
  v41 = v15;
  if ( g_wil_details_RecordSRUMFeatureUsage && (!a5 || a5 - 100 <= 0x31) )
    g_wil_details_RecordSRUMFeatureUsage(a2, a5, 1);
  if ( v12
    && wil::details::g_enabledStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !wil::details::g_enabledStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_39:
      ReleaseSRWLockExclusive(&SRWLock);
      v15 = v41;
      goto LABEL_40;
    }
    dwLowDateTime = 0;
    pftDueTime = 0;
    v18 = qword_180092150;
    v19 = qword_180092150 - (_QWORD)Source;
    v20 = (unsigned int *)qword_180092148;
    if ( (_BYTE *)qword_180092148 - (_BYTE *)Source + 16 >= (unsigned __int64)(qword_180092150 - (_QWORD)Source) )
    {
      v21 = 16;
      if ( 2 * v19 > 0x10 )
        v21 = 2 * v19;
      if ( v19 < v21 )
      {
        LastError = GetLastError();
        v23 = (v21 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v25 = (char *)wil::details::ProcessHeapAlloc(0, v23, v24);
        v26 = v25;
        if ( !v25 )
        {
          SetLastError(LastError);
          goto LABEL_32;
        }
        v27 = (_BYTE *)qword_180092148 - (_BYTE *)Source;
        memcpy_s(v25, v23, Source, (_BYTE *)qword_180092148 - (_BYTE *)Source);
        v28 = lpMem;
        lpMem = v26;
        if ( v28 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v28);
        }
        Source = v26;
        qword_180092148 = &v26[v27];
        qword_180092150 = (__int64)&v26[v23];
        SetLastError(LastError);
        v18 = qword_180092150;
        v20 = (unsigned int *)qword_180092148;
        v8 = a3;
        dwLowDateTime = pftDueTime.dwLowDateTime;
      }
    }
    v30 = 0;
    if ( (unsigned __int64)v20 < v18 )
      v30 = v18 - (_QWORD)v20;
    if ( v20 )
    {
      if ( v30 >= 0x10 )
      {
        *v20 = a2;
        v20[1] = dwLowDateTime;
        *((_QWORD *)v20 + 1) = a1;
LABEL_31:
        qword_180092148 = (char *)qword_180092148 + 16;
LABEL_32:
        if ( !byte_180092138 )
        {
          v31 = pti;
          if ( pti )
            goto LABEL_37;
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
LABEL_37:
            pftDueTime = (_FILETIME)-3000000000LL;
            SetThreadpoolTimer(v31, &pftDueTime, 0, 0x124F8u);
            byte_180092138 = 1;
          }
        }
        v13 = v46;
        v14 = v47;
        goto LABEL_39;
      }
      memset_0(v20, 0, v30);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v16, v19, v30) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_31;
  }
LABEL_40:
  if ( v13 )
  {
    v36 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v36 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v36(a2, v14, v13, 0);
    }
  }
  if ( !v15 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_180092188 )
    {
      qword_180092188 = 0;
      v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v37 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), __int64))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v37(&qword_180092188, _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_, -1);
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v8 )
  {
    v38 = a5;
    LODWORD(v38) = a5 | 0x80000000;
    if ( !a4 )
      v38 = a5;
    v39 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v39 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v39(a2, v38, 0, 0);
    }
  }
  if ( v15 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
    g_wil_details_realtimeFeatureUsageHook(a2, a5, a8);
  return 1;
}

```

## disassembly

```asm
0x180008e70  mov     [rsp+arg_0], rbx
0x180008e75  mov     [rsp+arg_18], r9d
0x180008e7a  mov     [rsp+arg_10], r8d
0x180008e7f  push    rbp
0x180008e80  push    rsi
0x180008e81  push    rdi
0x180008e82  push    r12
0x180008e84  push    r13
0x180008e86  push    r14
0x180008e88  push    r15
0x180008e8a  sub     rsp, 60h
0x180008e8e  mov     r15d, r8d
0x180008e91  mov     r12d, edx
0x180008e94  mov     r13, rcx
0x180008e97  mov     esi, [rsp+98h+arg_20]
0x180008e9e  mov     r8d, esi
0x180008ea1  mov     rdx, rcx
0x180008ea4  lea     rcx, [rsp+98h+var_58]
0x180008ea9  call    wil_details_FeatureReporting_RecordUsageInCache
0x180008eae  mov     ebx, [rax]
0x180008eb0  mov     edi, [rax+4]
0x180008eb3  mov     [rsp+98h+arg_28], edi
0x180008eba  mov     r14d, [rax+8]
0x180008ebe  mov     [rsp+98h+arg_30], r14d
0x180008ec6  mov     ebp, [rax+10h]
0x180008ec9  mov     [rsp+98h+var_68], ebp
0x180008ecd  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180008ed4  test    rax, rax
0x180008ed7  jz      short loc_180008EF5
0x180008ed9  test    esi, esi
0x180008edb  jz      short loc_180008EE5
0x180008edd  lea     ecx, [rsi-64h]
0x180008ee0  cmp     ecx, 31h ; '1'
0x180008ee3  ja      short loc_180008EF5
0x180008ee5  mov     r8d, 1
0x180008eeb  mov     edx, esi
0x180008eed  mov     ecx, r12d
0x180008ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef5  test    ebx, ebx
0x180008ef7  jz      loc_1800091B8
0x180008efd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008f03  test    eax, eax
0x180008f05  jz      loc_1800091B8
0x180008f0b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008f12  jnz     loc_1800091B8
0x180008f18  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008f1f  test    rax, rax
0x180008f22  jz      short loc_180008F31
0x180008f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f29  test    al, al
0x180008f2b  jnz     loc_1800091B8
0x180008f31  lea     rcx, SRWLock; SRWLock
0x180008f38  call    cs:__imp_AcquireSRWLockExclusive
0x180008f3e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008f44  test    eax, eax
0x180008f46  jz      loc_1800091A7
0x180008f4c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008f53  jnz     loc_1800091A7
0x180008f59  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008f60  test    rax, rax
0x180008f63  jz      short loc_180008F72
0x180008f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f6a  test    al, al
0x180008f6c  jnz     loc_1800091A7
0x180008f72  xor     r11d, r11d
0x180008f75  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], r11
0x180008f7a  mov     r10, cs:qword_180092150
0x180008f81  mov     rdx, r10
0x180008f84  sub     rdx, cs:Source
0x180008f8b  mov     r9, cs:qword_180092148
0x180008f92  mov     rax, r9
0x180008f95  sub     rax, cs:Source
0x180008f9c  add     rax, 10h
0x180008fa0  cmp     rax, rdx
0x180008fa3  jb      loc_180009077
0x180008fa9  lea     rax, [rdx+rdx]
0x180008fad  mov     ebx, 10h
0x180008fb2  cmp     rax, rbx
0x180008fb5  cmova   rbx, rax
0x180008fb9  cmp     rdx, rbx
0x180008fbc  jnb     loc_180009077
0x180008fc2  call    cs:__imp_GetLastError
0x180008fc8  mov     edi, eax
0x180008fca  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180008fce  lea     r14, [rbx+40h]
0x180008fd2  mov     rdx, r14; dwBytes
0x180008fd5  xor     ecx, ecx; dwFlags
0x180008fd7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008fdc  mov     rbx, rax
0x180008fdf  test    rax, rax
0x180008fe2  jnz     short loc_180008FF1
0x180008fe4  mov     ecx, edi; dwErrCode
0x180008fe6  call    cs:__imp_SetLastError
0x180008fec  jmp     loc_1800090D0
0x180008ff1  mov     r8, cs:Source; Source
0x180008ff8  mov     r15, cs:qword_180092148
0x180008fff  sub     r15, r8
0x180009002  mov     r9, r15; SourceSize
0x180009005  mov     rdx, r14; DestinationSize
0x180009008  mov     rcx, rbx; Destination
0x18000900b  call    memcpy_s
0x180009010  mov     rbp, cs:lpMem
0x180009017  mov     cs:lpMem, rbx
0x18000901e  test    rbp, rbp
0x180009021  jz      short loc_180009037
0x180009023  call    cs:__imp_GetProcessHeap
0x180009029  mov     rcx, rax; hHeap
0x18000902c  mov     r8, rbp; lpMem
0x18000902f  xor     edx, edx; dwFlags
0x180009031  call    cs:__imp_HeapFree
0x180009037  mov     cs:Source, rbx
0x18000903e  lea     rax, [r15+rbx]
0x180009042  mov     cs:qword_180092148, rax
0x180009049  lea     rax, [r14+rbx]
0x18000904d  mov     cs:qword_180092150, rax
0x180009054  mov     ecx, edi; dwErrCode
0x180009056  call    cs:__imp_SetLastError
0x18000905c  mov     r10, cs:qword_180092150
0x180009063  mov     r9, cs:qword_180092148
0x18000906a  mov     r15d, [rsp+98h+arg_10]
0x180009072  mov     r11, qword ptr [rsp+98h+pftDueTime.dwLowDateTime]
0x180009077  mov     rax, r10
0x18000907a  sub     rax, r9
0x18000907d  xor     r8d, r8d
0x180009080  cmp     r9, r10
0x180009083  cmovb   r8, rax; Size
0x180009087  test    r9, r9
0x18000908a  jnz     short loc_18000909A
0x18000908c  call    cs:__imp__o__errno
0x180009092  mov     dword ptr [rax], 16h
0x180009098  jmp     short loc_1800090C3
0x18000909a  cmp     r8, 10h
0x18000909e  jb      short loc_1800090AD
0x1800090a0  mov     [r9], r12d
0x1800090a3  mov     [r9+4], r11d
0x1800090a7  mov     [r9+8], r13
0x1800090ab  jmp     short loc_1800090C8
0x1800090ad  xor     edx, edx; Val
0x1800090af  mov     rcx, r9; void *
0x1800090b2  call    memset_0
0x1800090b7  call    cs:__imp__o__errno
0x1800090bd  mov     dword ptr [rax], 22h ; '"'
0x1800090c3  call    _invalid_parameter_noinfo
0x1800090c8  add     cs:qword_180092148, 10h
0x1800090d0  cmp     cs:byte_180092138, 0
0x1800090d7  jnz     loc_180009198
0x1800090dd  mov     rcx, cs:pti
0x1800090e4  test    rcx, rcx
0x1800090e7  jnz     loc_18000916E
0x1800090ed  call    cs:__imp_GetLastError
0x1800090f3  mov     ebp, eax
0x1800090f5  xor     r8d, r8d; pcbe
0x1800090f8  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800090ff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009106  call    cs:__imp_CreateThreadpoolTimer
0x18000910c  mov     r14, rax
0x18000910f  mov     rdi, cs:pti
0x180009116  test    rdi, rdi
0x180009119  jz      short loc_180009153
0x18000911b  call    cs:__imp_GetLastError
0x180009121  mov     ebx, eax
0x180009123  xor     r9d, r9d; msWindowLength
0x180009126  xor     r8d, r8d; msPeriod
0x180009129  xor     edx, edx; pftDueTime
0x18000912b  mov     rcx, rdi; pti
0x18000912e  call    cs:__imp_SetThreadpoolTimer
0x180009134  mov     edx, 1; fCancelPendingCallbacks
0x180009139  mov     rcx, rdi; pti
0x18000913c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009142  mov     rcx, rdi; pti
0x180009145  call    cs:__imp_CloseThreadpoolTimer
0x18000914b  mov     ecx, ebx; dwErrCode
0x18000914d  call    cs:__imp_SetLastError
0x180009153  mov     cs:pti, r14
0x18000915a  mov     ecx, ebp; dwErrCode
0x18000915c  call    cs:__imp_SetLastError
0x180009162  mov     rcx, cs:pti; pti
0x180009169  test    rcx, rcx
0x18000916c  jz      short loc_180009198
0x18000916e  mov     rax, 0FFFFFFFF4D2FA200h
0x180009178  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x18000917d  mov     r9d, 124F8h; msWindowLength
0x180009183  xor     r8d, r8d; msPeriod
0x180009186  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x18000918b  call    cs:__imp_SetThreadpoolTimer
0x180009191  mov     cs:byte_180092138, 1
0x180009198  mov     edi, [rsp+98h+arg_28]
0x18000919f  mov     r14d, [rsp+98h+arg_30]
0x1800091a7  lea     rcx, SRWLock; SRWLock
0x1800091ae  call    cs:__imp_ReleaseSRWLockExclusive
0x1800091b4  mov     ebp, [rsp+98h+var_68]
0x1800091b8  test    edi, edi
0x1800091ba  jz      short loc_1800091E5
0x1800091bc  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800091c3  test    rax, rax
0x1800091c6  jnz     short loc_1800091D4
0x1800091c8  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800091cf  test    rax, rax
0x1800091d2  jz      short loc_1800091E5
0x1800091d4  xor     r9d, r9d
0x1800091d7  mov     r8d, edi
0x1800091da  mov     edx, r14d
0x1800091dd  mov     ecx, r12d
0x1800091e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e5  test    ebp, ebp
0x1800091e7  jnz     short loc_180009255
0x1800091e9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800091ef  test    eax, eax
0x1800091f1  jz      short loc_180009255
0x1800091f3  lea     rcx, SRWLock; SRWLock
0x1800091fa  call    cs:__imp_AcquireSRWLockExclusive
0x180009200  cmp     cs:qword_180092188, 0
0x180009208  jnz     short loc_180009247
0x18000920a  mov     cs:qword_180092188, 0
0x180009215  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000921c  test    rax, rax
0x18000921f  jnz     short loc_18000922D
0x180009221  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180009228  test    rax, rax
0x18000922b  jz      short loc_180009247
0x18000922d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180009234  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; _lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_(void *)
0x18000923b  lea     rcx, qword_180092188
0x180009242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009247  lea     rcx, SRWLock; SRWLock
0x18000924e  call    cs:__imp_ReleaseSRWLockExclusive
0x180009254  nop
0x180009255  test    r15d, r15d
0x180009258  jz      short loc_180009291
0x18000925a  mov     edx, esi
0x18000925c  bts     edx, 1Fh
0x180009260  cmp     [rsp+98h+arg_18], 0
0x180009268  cmovz   edx, esi
0x18000926b  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180009272  test    rax, rax
0x180009275  jnz     short loc_180009283
0x180009277  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000927e  test    rax, rax
0x180009281  jz      short loc_180009291
0x180009283  xor     r9d, r9d
0x180009286  xor     r8d, r8d
0x180009289  mov     ecx, r12d
0x18000928c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009291  test    ebp, ebp
0x180009293  jnz     short loc_1800092BB
0x180009295  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000929c  test    rax, rax
0x18000929f  jz      short loc_1800092B4
0x1800092a1  movzx   r8d, [rsp+98h+arg_38]
0x1800092aa  mov     edx, esi
0x1800092ac  mov     ecx, r12d
0x1800092af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b4  mov     eax, 1
0x1800092b9  jmp     short loc_1800092BD
0x1800092bb  xor     eax, eax
0x1800092bd  mov     rbx, [rsp+98h+arg_0]
0x1800092c5  add     rsp, 60h
0x1800092c9  pop     r15
0x1800092cb  pop     r14
0x1800092cd  pop     r13
0x1800092cf  pop     r12
0x1800092d1  pop     rdi
0x1800092d2  pop     rsi
0x1800092d3  pop     rbp
0x1800092d4  retn
```
