# UQIService::TimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18001c060`
- end: `0x18001c3c8`
- name: `?TimerCallback@UQIService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `872`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800033d0`
- `0x180008320`
- `0x180013c48`
- `0x1800149fc`
- `0x180016cac`
- `0x180016dcc`
- `0x180018e64`
- `0x18001ad68`
- `0x18001b234`
- `0x18001c060`
- `0x18002b6a8`
- `0x180036c7c`
- `0x1800f4eb4`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c35a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c35a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c32d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c32d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c1b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c1b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c082`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c09f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c082`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c09f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c0d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001c0d5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001c08b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18001c08b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001c0ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001c3a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001c0ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001c3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c1f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c1f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c384`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18001c0f0`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x18001c0f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall UQIService::TimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct _RTL_CRITICAL_SECTION *Context,
        PTP_TIMER Timer)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  HANDLE v6; // rax
  HANDLE CurrentProcess; // rax
  volatile signed __int32 **v8; // rax
  volatile signed __int32 *v9; // rdi
  void *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 *Local; // rax
  volatile signed __int32 *LockSemaphore; // rax
  volatile signed __int32 *v15; // rdi
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rsi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  volatile signed __int32 *v19; // rdi
  _DWORD *v20; // rdi
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  void *v22; // rdi
  HANDLE v23; // rax
  const char *v24; // rax
  int nPriority; // [rsp+24h] [rbp-C4h]
  UsageAndQualityInsights::Facts::FactStoreManager *SpinCount; // [rsp+28h] [rbp-C0h] BYREF
  volatile signed __int32 *v27; // [rsp+30h] [rbp-B8h]
  void **v28; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD v29[2]; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-90h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-88h]
  __int64 v32; // [rsp+68h] [rbp-80h]
  char v33; // [rsp+70h] [rbp-78h]
  LPVOID v34; // [rsp+78h] [rbp-70h]
  LPVOID pv[2]; // [rsp+80h] [rbp-68h] BYREF
  const wil::ResultException *v36; // [rsp+90h] [rbp-58h] BYREF
  const std::exception *v37; // [rsp+98h] [rbp-50h] BYREF
  _DWORD v38[4]; // [rsp+A0h] [rbp-48h] BYREF

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority == 0x7FFFFFFF )
    ThreadPriority = 0;
  nPriority = ThreadPriority;
  v6 = GetCurrentThread();
  SetThreadPriority(v6, -15);
  v38[0] = 1;
  v38[1] = 1;
  v38[2] = 1;
  CurrentProcess = GetCurrentProcess();
  SetProcessInformation(CurrentProcess, 4, v38);
  v8 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIRunBackgroundTaskTipTest,_tip_UQIRunBackgroundTaskTipTest>,>(pv);
  v9 = *v8;
  *v8 = 0;
  v10 = pv[0];
  if ( pv[0] && _InterlockedExchangeAdd((volatile signed __int32 *)pv[0] + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v10);
    CoTaskMemFree(v10);
  }
  tip2::details::shared_data<0,0,0>::start(v9 + 2, &SpinCount);
  v28 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v29[0] = 0;
  v29[1] = &v28;
  v30 = 0;
  CurrentThreadId = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v11) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v12,
                         v11);
    v29[0] = Local;
    if ( Local )
    {
      v30 = *Local;
      *Local = (__int64)v29;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v29[0] = 0;
  }
  v34 = (LPVOID)v9;
  if ( v9 )
  {
    _InterlockedIncrement(v9 + 68);
    if ( !_InterlockedDecrement(v9 + 68) )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v9);
      CoTaskMemFree((LPVOID)v9);
    }
  }
  try
  {
    UQIService::EnsureInitialized(Context);
    LockSemaphore = (volatile signed __int32 *)Context[1].LockSemaphore;
    if ( LockSemaphore )
      _InterlockedIncrement(LockSemaphore + 2);
    pv[0] = Context[1].OwningThread;
    v15 = (volatile signed __int32 *)Context[1].LockSemaphore;
    pv[1] = (LPVOID)v15;
    v16 = *(_QWORD *)UsageAndQualityInsights::Database::UQIDatabaseManager::GetOrCreateServiceUsageDatabase(
                       pv[0],
                       &SpinCount);
    UsageAndQualityInsights::Database::ServiceUsageDatabase::IncrementServiceUsage(v16);
    v17 = v27;
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl'::`2'::impl) )
    {
      DebugInfo = Context[2].DebugInfo;
      if ( DebugInfo )
        _InterlockedIncrement((volatile signed __int32 *)&DebugInfo->CriticalSection);
      SpinCount = (UsageAndQualityInsights::Facts::FactStoreManager *)Context[1].SpinCount;
      v27 = (volatile signed __int32 *)Context[2].DebugInfo;
      v19 = v27;
      UsageAndQualityInsights::Facts::FactStoreManager::CleanupFactTables(SpinCount);
      if ( v19 )
      {
        if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
    }
    v20 = v34;
    v21 = (struct _RTL_CRITICAL_SECTION *)((char *)v34 + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)v34 + 5);
    v20[18] |= 0x300u;
    if ( *((_QWORD *)v20 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v20 + 2, 2);
    if ( v21 )
      LeaveCriticalSection(v21);
    v22 = v34;
    if ( v34 && _InterlockedExchangeAdd((volatile signed __int32 *)v34 + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v22);
      CoTaskMemFree(v22);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v29);
  }
  catch ( const wil::ResultException *v36 )
  {
    UsageAndQualityInsightsCoreLogging::TraceLoggingError(
      "Background maintenance task failed, error: 0x%08X",
      *((_DWORD *)v36 + 8));
  }
  catch ( const std::exception *v37 )
  {
    v24 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v37 + 8LL))(v37);
    UsageAndQualityInsightsCoreLogging::TraceLoggingError("Background maintenance task failed, exception: %s", v24);
  }
  v23 = GetCurrentThread();
  SetThreadPriority(v23, nPriority);
}

```

## disassembly

```asm
0x18001c060  push    rbx
0x18001c062  push    rsi
0x18001c063  push    rdi
0x18001c064  push    r14
0x18001c066  sub     rsp, 0C8h
0x18001c06d  mov     rax, cs:__security_cookie
0x18001c074  xor     rax, rsp
0x18001c077  mov     [rsp+0E8h+var_38], rax
0x18001c07f  mov     r14, rdx
0x18001c082  call    cs:__imp_GetCurrentThread
0x18001c088  mov     rcx, rax; hThread
0x18001c08b  call    cs:__imp_GetThreadPriority
0x18001c091  xor     ecx, ecx
0x18001c093  cmp     eax, 7FFFFFFFh
0x18001c098  cmovz   eax, ecx
0x18001c09b  mov     [rsp+0E8h+nPriority], eax
0x18001c09f  call    cs:__imp_GetCurrentThread
0x18001c0a5  mov     rcx, rax; hThread
0x18001c0a8  mov     edx, 0FFFFFFF1h; nPriority
0x18001c0ad  call    cs:__imp_SetThreadPriority
0x18001c0b3  nop
0x18001c0b4  mov     [rsp+0E8h+var_48], 1
0x18001c0bf  mov     [rsp+0E8h+var_44], 1
0x18001c0ca  mov     [rsp+0E8h+var_40], 1
0x18001c0d5  call    cs:__imp_GetCurrentProcess
0x18001c0db  mov     rcx, rax
0x18001c0de  mov     r9d, 0Ch
0x18001c0e4  lea     r8, [rsp+0E8h+var_48]
0x18001c0ec  lea     edx, [r9-8]
0x18001c0f0  call    cs:__imp_SetProcessInformation
0x18001c0f6  nop
0x18001c0f7  lea     rcx, [rsp+0E8h+pv]
0x18001c0ff  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIRunBackgroundTaskTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIRunBackgroundTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIRunBackgroundTaskTipTest,_tip_UQIRunBackgroundTaskTipTest>,>(void)
0x18001c104  mov     rdi, [rax]
0x18001c107  mov     qword ptr [rax], 0
0x18001c10e  mov     rsi, [rsp+0E8h+pv]
0x18001c116  or      ebx, 0FFFFFFFFh
0x18001c119  test    rsi, rsi
0x18001c11c  jz      short loc_18001C13D
0x18001c11e  mov     eax, ebx
0x18001c120  lock xadd [rsi+110h], eax
0x18001c128  add     eax, ebx
0x18001c12a  jnz     short loc_18001C13D
0x18001c12c  mov     rcx, rsi
0x18001c12f  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18001c134  mov     rcx, rsi; pv
0x18001c137  call    cs:__imp_CoTaskMemFree
0x18001c13d  lea     rcx, [rdi+8]
0x18001c141  lea     rdx, [rsp+0E8h+var_C0]
0x18001c146  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001c14b  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x18001c152  mov     [rsp+0E8h+var_A8], rax
0x18001c157  mov     [rsp+0E8h+var_A0], 0
0x18001c160  lea     rax, [rsp+0E8h+var_A8]
0x18001c165  mov     [rsp+0E8h+var_98], rax
0x18001c16a  mov     [rsp+0E8h+var_90], 0
0x18001c173  mov     [rsp+0E8h+var_88], 0
0x18001c17b  mov     [rsp+0E8h+var_80], 0
0x18001c184  mov     [rsp+0E8h+var_78], 0
0x18001c189  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001c191  jz      short loc_18001C1C0
0x18001c193  mov     dl, 1
0x18001c195  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001c19a  mov     [rsp+0E8h+var_A0], rax
0x18001c19f  test    rax, rax
0x18001c1a2  jz      short loc_18001C1C9
0x18001c1a4  mov     rcx, [rax]
0x18001c1a7  mov     [rsp+0E8h+var_90], rcx
0x18001c1ac  lea     rcx, [rsp+0E8h+var_A0]
0x18001c1b1  mov     [rax], rcx
0x18001c1b4  call    cs:__imp_GetCurrentThreadId
0x18001c1ba  mov     [rsp+0E8h+var_88], eax
0x18001c1be  jmp     short loc_18001C1C9
0x18001c1c0  mov     [rsp+0E8h+var_A0], 0
0x18001c1c9  mov     [rsp+0E8h+var_70], rdi
0x18001c1ce  test    rdi, rdi
0x18001c1d1  jz      short loc_18001C1FA
0x18001c1d3  lock inc dword ptr [rdi+110h]
0x18001c1da  mov     eax, ebx
0x18001c1dc  lock xadd [rdi+110h], eax
0x18001c1e4  add     eax, ebx
0x18001c1e6  jnz     short loc_18001C1FA
0x18001c1e8  mov     rcx, rdi
0x18001c1eb  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18001c1f0  mov     rcx, rdi; pv
0x18001c1f3  call    cs:__imp_CoTaskMemFree
0x18001c1f9  nop
0x18001c1fa  mov     rcx, r14; pv
0x18001c1fd  call    ?EnsureInitialized@UQIService@@QEAAXXZ; UQIService::EnsureInitialized(void)
0x18001c202  mov     rax, [r14+40h]
0x18001c206  test    rax, rax
0x18001c209  jz      short loc_18001C20F
0x18001c20b  lock inc dword ptr [rax+8]
0x18001c20f  mov     rcx, [r14+38h]
0x18001c213  mov     [rsp+0E8h+pv], rcx
0x18001c21b  mov     rdi, [r14+40h]
0x18001c21f  mov     [rsp+0E8h+var_60], rdi
0x18001c227  lea     rdx, [rsp+0E8h+var_C0]
0x18001c22c  call    ?GetOrCreateServiceUsageDatabase@UQIDatabaseManager@Database@UsageAndQualityInsights@@QEAA?AV?$shared_ptr@VServiceUsageDatabase@Database@UsageAndQualityInsights@@@std@@XZ; UsageAndQualityInsights::Database::UQIDatabaseManager::GetOrCreateServiceUsageDatabase(void)
0x18001c231  nop
0x18001c232  mov     rcx, [rax]
0x18001c235  call    ?IncrementServiceUsage@ServiceUsageDatabase@Database@UsageAndQualityInsights@@QEAAXW4ServiceUsageKind@23@@Z; UsageAndQualityInsights::Database::ServiceUsageDatabase::IncrementServiceUsage(UsageAndQualityInsights::Database::ServiceUsageKind)
0x18001c23a  nop
0x18001c23b  mov     rsi, [rsp+0E8h+var_B8]
0x18001c240  test    rsi, rsi
0x18001c243  jz      short loc_18001C279
0x18001c245  mov     eax, ebx
0x18001c247  lock xadd [rsi+8], eax
0x18001c24c  add     eax, ebx
0x18001c24e  jnz     short loc_18001C279
0x18001c250  mov     rax, [rsi]
0x18001c253  mov     rcx, rsi
0x18001c256  mov     rax, [rax]
0x18001c259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c25e  mov     eax, ebx
0x18001c260  lock xadd [rsi+0Ch], eax
0x18001c265  add     eax, ebx
0x18001c267  jnz     short loc_18001C279
0x18001c269  mov     rax, [rsi]
0x18001c26c  mov     rcx, rsi
0x18001c26f  mov     rax, [rax+8]
0x18001c273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c278  nop
0x18001c279  test    rdi, rdi
0x18001c27c  jz      short loc_18001C2B1
0x18001c27e  mov     eax, ebx
0x18001c280  lock xadd [rdi+8], eax
0x18001c285  add     eax, ebx
0x18001c287  jnz     short loc_18001C2B1
0x18001c289  mov     rax, [rdi]
0x18001c28c  mov     rcx, rdi
0x18001c28f  mov     rax, [rax]
0x18001c292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c297  mov     eax, ebx
0x18001c299  lock xadd [rdi+0Ch], eax
0x18001c29e  add     eax, ebx
0x18001c2a0  jnz     short loc_18001C2B1
0x18001c2a2  mov     rax, [rdi]
0x18001c2a5  mov     rcx, rdi
0x18001c2a8  mov     rax, [rax+8]
0x18001c2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59192442@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59192442@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442> `wil::Feature<__WilFeatureTraits_Feature_59192442>::GetImpl(void)'::`2'::impl
0x18001c2b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59192442@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59192442>::__private_IsEnabled(void)
0x18001c2bd  test    al, al
0x18001c2bf  jz      short loc_18001C31E
0x18001c2c1  mov     rax, [r14+50h]
0x18001c2c5  test    rax, rax
0x18001c2c8  jz      short loc_18001C2CE
0x18001c2ca  lock inc dword ptr [rax+8]
0x18001c2ce  mov     rcx, [r14+48h]; this
0x18001c2d2  mov     [rsp+0E8h+var_C0], rcx
0x18001c2d7  mov     rdi, [r14+50h]
0x18001c2db  mov     [rsp+0E8h+var_B8], rdi
0x18001c2e0  call    ?CleanupFactTables@FactStoreManager@Facts@UsageAndQualityInsights@@QEAAXXZ; UsageAndQualityInsights::Facts::FactStoreManager::CleanupFactTables(void)
0x18001c2e5  nop
0x18001c2e6  test    rdi, rdi
0x18001c2e9  jz      short loc_18001C31E
0x18001c2eb  mov     eax, ebx
0x18001c2ed  lock xadd [rdi+8], eax
0x18001c2f2  add     eax, ebx
0x18001c2f4  jnz     short loc_18001C31E
0x18001c2f6  mov     rax, [rdi]
0x18001c2f9  mov     rcx, rdi
0x18001c2fc  mov     rax, [rax]
0x18001c2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c304  mov     eax, ebx
0x18001c306  lock xadd [rdi+0Ch], eax
0x18001c30b  add     eax, ebx
0x18001c30d  jnz     short loc_18001C31E
0x18001c30f  mov     rax, [rdi]
0x18001c312  mov     rcx, rdi
0x18001c315  mov     rax, [rax+8]
0x18001c319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c31e  mov     rdi, [rsp+0E8h+var_70]
0x18001c323  lea     rsi, [rdi+0C8h]
0x18001c32a  mov     rcx, rsi; lpCriticalSection
0x18001c32d  call    cs:__imp_EnterCriticalSection
0x18001c333  or      dword ptr [rdi+48h], 300h
0x18001c33a  cmp     qword ptr [rdi+0F8h], 0
0x18001c342  jz      short loc_18001C352
0x18001c344  mov     edx, 2
0x18001c349  lea     rcx, [rdi+8]
0x18001c34d  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001c352  test    rsi, rsi
0x18001c355  jz      short loc_18001C361
0x18001c357  mov     rcx, rsi; lpCriticalSection
0x18001c35a  call    cs:__imp_LeaveCriticalSection
0x18001c360  nop
0x18001c361  mov     rdi, [rsp+0E8h+var_70]
0x18001c366  test    rdi, rdi
0x18001c369  jz      short loc_18001C38A
0x18001c36b  mov     eax, ebx
0x18001c36d  lock xadd [rdi+110h], eax
0x18001c375  add     eax, ebx
0x18001c377  jnz     short loc_18001C38A
0x18001c379  mov     rcx, rdi
0x18001c37c  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18001c381  mov     rcx, rdi; pv
0x18001c384  call    cs:__imp_CoTaskMemFree
0x18001c38a  lea     rcx, [rsp+0E8h+var_A0]; this
0x18001c38f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001c394  nop
0x18001c395  call    cs:__imp_GetCurrentThread
0x18001c39b  mov     edx, [rsp+0E8h+nPriority]; nPriority
0x18001c39f  mov     rcx, rax; hThread
0x18001c3a2  call    cs:__imp_SetThreadPriority
0x18001c3a8  mov     rcx, [rsp+0E8h+var_38]
0x18001c3b0  xor     rcx, rsp; StackCookie
0x18001c3b3  call    __security_check_cookie
0x18001c3b8  add     rsp, 0C8h
0x18001c3bf  pop     r14
0x18001c3c1  pop     rdi
0x18001c3c2  pop     rsi
0x18001c3c3  pop     rbx
0x18001c3c4  retn
0x18001c3c5  jmp     short loc_18001C395
```
