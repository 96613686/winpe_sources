# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180007480`
- end: `0x18000766e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a690`

## callees

- `0x18000733c`
- `0x180007480`
- `0x1800090c0`
- `0x180009618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800075a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800075e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800075a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800075e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000753e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000758e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000753e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000758e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000754c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000759c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000754c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000759c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000749e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000749e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007519`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800074d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007519`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800074bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007508`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000760e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000763f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800074bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007508`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000760e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000763f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800074c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007511`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007617`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007648`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800074c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007511`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007617`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007648`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007600`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007631`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007600`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007631`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_180010028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180010028[25], qword_180010028, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x180007480  mov     [rsp+arg_0], rbx
0x180007485  mov     [rsp+arg_8], rsi
0x18000748a  push    rdi
0x18000748b  sub     rsp, 20h
0x18000748f  mov     rdi, rcx
0x180007492  mov     byte ptr [rcx], 0
0x180007495  mov     rsi, [rcx+30h]
0x180007499  test    rsi, rsi
0x18000749c  jz      short loc_1800074D6
0x18000749e  call    cs:__imp_GetLastError
0x1800074a4  mov     ebx, eax
0x1800074a6  xor     r9d, r9d; msWindowLength
0x1800074a9  xor     r8d, r8d; msPeriod
0x1800074ac  xor     edx, edx; pftDueTime
0x1800074ae  mov     rcx, rsi; pti
0x1800074b1  call    cs:__imp_SetThreadpoolTimer
0x1800074b7  mov     edx, 1; fCancelPendingCallbacks
0x1800074bc  mov     rcx, rsi; pti
0x1800074bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800074c5  mov     rcx, rsi; pti
0x1800074c8  call    cs:__imp_CloseThreadpoolTimer
0x1800074ce  mov     ecx, ebx; dwErrCode
0x1800074d0  call    cs:__imp_SetLastError
0x1800074d6  mov     qword ptr [rdi+30h], 0
0x1800074de  mov     rsi, [rdi+38h]
0x1800074e2  test    rsi, rsi
0x1800074e5  jz      short loc_18000751F
0x1800074e7  call    cs:__imp_GetLastError
0x1800074ed  mov     ebx, eax
0x1800074ef  xor     r9d, r9d; msWindowLength
0x1800074f2  xor     r8d, r8d; msPeriod
0x1800074f5  xor     edx, edx; pftDueTime
0x1800074f7  mov     rcx, rsi; pti
0x1800074fa  call    cs:__imp_SetThreadpoolTimer
0x180007500  mov     edx, 1; fCancelPendingCallbacks
0x180007505  mov     rcx, rsi; pti
0x180007508  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000750e  mov     rcx, rsi; pti
0x180007511  call    cs:__imp_CloseThreadpoolTimer
0x180007517  mov     ecx, ebx; dwErrCode
0x180007519  call    cs:__imp_SetLastError
0x18000751f  mov     qword ptr [rdi+38h], 0
0x180007527  mov     rbx, [rdi+100h]
0x18000752e  mov     qword ptr [rdi+100h], 0
0x180007539  test    rbx, rbx
0x18000753c  jz      short loc_180007552
0x18000753e  call    cs:__imp_GetProcessHeap
0x180007544  mov     rcx, rax; hHeap
0x180007547  mov     r8, rbx; lpMem
0x18000754a  xor     edx, edx; dwFlags
0x18000754c  call    cs:__imp_HeapFree
0x180007552  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180007559  test    r8, r8
0x18000755c  jz      short loc_180007576
0x18000755e  mov     rdx, cs:qword_180010028; SRWLock
0x180007565  test    rdx, rdx
0x180007568  jz      short loc_180007576
0x18000756a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007571  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180007576  lea     rbx, [rdi+98h]
0x18000757d  mov     rsi, [rbx+40h]
0x180007581  mov     qword ptr [rbx+40h], 0
0x180007589  test    rsi, rsi
0x18000758c  jz      short loc_1800075A2
0x18000758e  call    cs:__imp_GetProcessHeap
0x180007594  mov     rcx, rax; hHeap
0x180007597  mov     r8, rsi; lpMem
0x18000759a  xor     edx, edx; dwFlags
0x18000759c  call    cs:__imp_HeapFree
0x1800075a2  mov     rcx, rbx; lpCriticalSection
0x1800075a5  call    cs:__imp_DeleteCriticalSection
0x1800075ab  lea     rcx, [rdi+90h]
0x1800075b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800075b7  mov     rsi, [rdi+88h]
0x1800075be  mov     qword ptr [rdi+88h], 0
0x1800075c9  test    rsi, rsi
0x1800075cc  jz      short loc_1800075E2
0x1800075ce  call    cs:__imp_GetProcessHeap
0x1800075d4  mov     rcx, rax; hHeap
0x1800075d7  mov     r8, rsi; lpMem
0x1800075da  xor     edx, edx; dwFlags
0x1800075dc  call    cs:__imp_HeapFree
0x1800075e2  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800075e6  call    cs:__imp_DeleteCriticalSection
0x1800075ec  mov     rbx, [rdi+38h]
0x1800075f0  test    rbx, rbx
0x1800075f3  jz      short loc_18000761D
0x1800075f5  xor     r9d, r9d; msWindowLength
0x1800075f8  xor     r8d, r8d; msPeriod
0x1800075fb  xor     edx, edx; pftDueTime
0x1800075fd  mov     rcx, rbx; pti
0x180007600  call    cs:__imp_SetThreadpoolTimer
0x180007606  mov     edx, 1; fCancelPendingCallbacks
0x18000760b  mov     rcx, rbx; pti
0x18000760e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007614  mov     rcx, rbx; pti
0x180007617  call    cs:__imp_CloseThreadpoolTimer
0x18000761d  mov     rbx, [rdi+30h]
0x180007621  test    rbx, rbx
0x180007624  jz      short loc_18000764F
0x180007626  xor     r9d, r9d; msWindowLength
0x180007629  xor     r8d, r8d; msPeriod
0x18000762c  xor     edx, edx; pftDueTime
0x18000762e  mov     rcx, rbx; pti
0x180007631  call    cs:__imp_SetThreadpoolTimer
0x180007637  mov     edx, 1; fCancelPendingCallbacks
0x18000763c  mov     rcx, rbx; pti
0x18000763f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007645  mov     rcx, rbx; pti
0x180007648  call    cs:__imp_CloseThreadpoolTimer
0x18000764e  nop
0x18000764f  mov     rcx, [rdi+10h]; lpMem
0x180007653  test    rcx, rcx
0x180007656  jz      short loc_18000765E
0x180007658  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000765d  nop
0x18000765e  mov     rbx, [rsp+28h+arg_0]
0x180007663  mov     rsi, [rsp+28h+arg_8]
0x180007668  add     rsp, 20h
0x18000766c  pop     rdi
0x18000766d  retn
```
