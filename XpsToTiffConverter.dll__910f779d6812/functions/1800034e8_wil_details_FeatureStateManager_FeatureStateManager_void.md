# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800034e8`
- end: `0x1800036d6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d870`

## callees

- `0x1800033a4`
- `0x1800034e8`
- `0x180006d30`
- `0x1800081a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000360d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000364e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000360d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000364e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003644`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003644`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003636`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000354f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000354f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003538`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003581`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003538`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003581`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003530`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003579`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000367f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003530`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003579`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000367f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003519`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003562`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003668`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003699`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003519`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003562`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003668`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003699`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003527`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003570`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003676`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003527`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003570`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003676`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036a7`

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
  if ( v8 && qword_180014018 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180014018[25], qword_180014018, v8);
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
0x1800034e8  mov     [rsp+arg_0], rbx
0x1800034ed  mov     [rsp+arg_8], rsi
0x1800034f2  push    rdi
0x1800034f3  sub     rsp, 20h
0x1800034f7  mov     rdi, rcx
0x1800034fa  mov     byte ptr [rcx], 0
0x1800034fd  mov     rsi, [rcx+30h]
0x180003501  test    rsi, rsi
0x180003504  jz      short loc_18000353E
0x180003506  call    cs:__imp_GetLastError
0x18000350c  mov     ebx, eax
0x18000350e  xor     r9d, r9d; msWindowLength
0x180003511  xor     r8d, r8d; msPeriod
0x180003514  xor     edx, edx; pftDueTime
0x180003516  mov     rcx, rsi; pti
0x180003519  call    cs:__imp_SetThreadpoolTimer
0x18000351f  mov     edx, 1; fCancelPendingCallbacks
0x180003524  mov     rcx, rsi; pti
0x180003527  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000352d  mov     rcx, rsi; pti
0x180003530  call    cs:__imp_CloseThreadpoolTimer
0x180003536  mov     ecx, ebx; dwErrCode
0x180003538  call    cs:__imp_SetLastError
0x18000353e  mov     qword ptr [rdi+30h], 0
0x180003546  mov     rsi, [rdi+38h]
0x18000354a  test    rsi, rsi
0x18000354d  jz      short loc_180003587
0x18000354f  call    cs:__imp_GetLastError
0x180003555  mov     ebx, eax
0x180003557  xor     r9d, r9d; msWindowLength
0x18000355a  xor     r8d, r8d; msPeriod
0x18000355d  xor     edx, edx; pftDueTime
0x18000355f  mov     rcx, rsi; pti
0x180003562  call    cs:__imp_SetThreadpoolTimer
0x180003568  mov     edx, 1; fCancelPendingCallbacks
0x18000356d  mov     rcx, rsi; pti
0x180003570  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003576  mov     rcx, rsi; pti
0x180003579  call    cs:__imp_CloseThreadpoolTimer
0x18000357f  mov     ecx, ebx; dwErrCode
0x180003581  call    cs:__imp_SetLastError
0x180003587  mov     qword ptr [rdi+38h], 0
0x18000358f  mov     rbx, [rdi+100h]
0x180003596  mov     qword ptr [rdi+100h], 0
0x1800035a1  test    rbx, rbx
0x1800035a4  jz      short loc_1800035BA
0x1800035a6  call    cs:__imp_GetProcessHeap
0x1800035ac  mov     rcx, rax; hHeap
0x1800035af  mov     r8, rbx; lpMem
0x1800035b2  xor     edx, edx; dwFlags
0x1800035b4  call    cs:__imp_HeapFree
0x1800035ba  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800035c1  test    r8, r8
0x1800035c4  jz      short loc_1800035DE
0x1800035c6  mov     rdx, cs:qword_180014018; SRWLock
0x1800035cd  test    rdx, rdx
0x1800035d0  jz      short loc_1800035DE
0x1800035d2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800035d9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800035de  lea     rbx, [rdi+98h]
0x1800035e5  mov     rsi, [rbx+40h]
0x1800035e9  mov     qword ptr [rbx+40h], 0
0x1800035f1  test    rsi, rsi
0x1800035f4  jz      short loc_18000360A
0x1800035f6  call    cs:__imp_GetProcessHeap
0x1800035fc  mov     rcx, rax; hHeap
0x1800035ff  mov     r8, rsi; lpMem
0x180003602  xor     edx, edx; dwFlags
0x180003604  call    cs:__imp_HeapFree
0x18000360a  mov     rcx, rbx; lpCriticalSection
0x18000360d  call    cs:__imp_DeleteCriticalSection
0x180003613  lea     rcx, [rdi+90h]
0x18000361a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000361f  mov     rsi, [rdi+88h]
0x180003626  mov     qword ptr [rdi+88h], 0
0x180003631  test    rsi, rsi
0x180003634  jz      short loc_18000364A
0x180003636  call    cs:__imp_GetProcessHeap
0x18000363c  mov     rcx, rax; hHeap
0x18000363f  mov     r8, rsi; lpMem
0x180003642  xor     edx, edx; dwFlags
0x180003644  call    cs:__imp_HeapFree
0x18000364a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000364e  call    cs:__imp_DeleteCriticalSection
0x180003654  mov     rbx, [rdi+38h]
0x180003658  test    rbx, rbx
0x18000365b  jz      short loc_180003685
0x18000365d  xor     r9d, r9d; msWindowLength
0x180003660  xor     r8d, r8d; msPeriod
0x180003663  xor     edx, edx; pftDueTime
0x180003665  mov     rcx, rbx; pti
0x180003668  call    cs:__imp_SetThreadpoolTimer
0x18000366e  mov     edx, 1; fCancelPendingCallbacks
0x180003673  mov     rcx, rbx; pti
0x180003676  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000367c  mov     rcx, rbx; pti
0x18000367f  call    cs:__imp_CloseThreadpoolTimer
0x180003685  mov     rbx, [rdi+30h]
0x180003689  test    rbx, rbx
0x18000368c  jz      short loc_1800036B7
0x18000368e  xor     r9d, r9d; msWindowLength
0x180003691  xor     r8d, r8d; msPeriod
0x180003694  xor     edx, edx; pftDueTime
0x180003696  mov     rcx, rbx; pti
0x180003699  call    cs:__imp_SetThreadpoolTimer
0x18000369f  mov     edx, 1; fCancelPendingCallbacks
0x1800036a4  mov     rcx, rbx; pti
0x1800036a7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036ad  mov     rcx, rbx; pti
0x1800036b0  call    cs:__imp_CloseThreadpoolTimer
0x1800036b6  nop
0x1800036b7  mov     rcx, [rdi+10h]; lpMem
0x1800036bb  test    rcx, rcx
0x1800036be  jz      short loc_1800036C6
0x1800036c0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800036c5  nop
0x1800036c6  mov     rbx, [rsp+28h+arg_0]
0x1800036cb  mov     rsi, [rsp+28h+arg_8]
0x1800036d0  add     rsp, 20h
0x1800036d4  pop     rdi
0x1800036d5  retn
```
