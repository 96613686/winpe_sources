# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180008394`
- end: `0x180008582`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011260`

## callees

- `0x180008250`
- `0x180008394`
- `0x18000ba74`
- `0x18000c6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800084f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800084e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000842d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000842d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008425`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000852b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000855c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008425`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000852b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000855c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000840e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008514`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008545`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000840e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008514`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008545`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000841c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008522`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008553`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000841c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008522`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008553`

## pseudocode

```c
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
  if ( v8 && qword_180019098 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180019098[25], qword_180019098, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
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
0x180008394  mov     [rsp+arg_0], rbx
0x180008399  mov     [rsp+arg_8], rsi
0x18000839e  push    rdi
0x18000839f  sub     rsp, 20h
0x1800083a3  mov     rdi, rcx
0x1800083a6  mov     byte ptr [rcx], 0
0x1800083a9  mov     rsi, [rcx+30h]
0x1800083ad  test    rsi, rsi
0x1800083b0  jz      short loc_1800083EA
0x1800083b2  call    cs:__imp_GetLastError
0x1800083b8  mov     ebx, eax
0x1800083ba  xor     r9d, r9d; msWindowLength
0x1800083bd  xor     r8d, r8d; msPeriod
0x1800083c0  xor     edx, edx; pftDueTime
0x1800083c2  mov     rcx, rsi; pti
0x1800083c5  call    cs:__imp_SetThreadpoolTimer
0x1800083cb  mov     edx, 1; fCancelPendingCallbacks
0x1800083d0  mov     rcx, rsi; pti
0x1800083d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800083d9  mov     rcx, rsi; pti
0x1800083dc  call    cs:__imp_CloseThreadpoolTimer
0x1800083e2  mov     ecx, ebx; dwErrCode
0x1800083e4  call    cs:__imp_SetLastError
0x1800083ea  mov     qword ptr [rdi+30h], 0
0x1800083f2  mov     rsi, [rdi+38h]
0x1800083f6  test    rsi, rsi
0x1800083f9  jz      short loc_180008433
0x1800083fb  call    cs:__imp_GetLastError
0x180008401  mov     ebx, eax
0x180008403  xor     r9d, r9d; msWindowLength
0x180008406  xor     r8d, r8d; msPeriod
0x180008409  xor     edx, edx; pftDueTime
0x18000840b  mov     rcx, rsi; pti
0x18000840e  call    cs:__imp_SetThreadpoolTimer
0x180008414  mov     edx, 1; fCancelPendingCallbacks
0x180008419  mov     rcx, rsi; pti
0x18000841c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008422  mov     rcx, rsi; pti
0x180008425  call    cs:__imp_CloseThreadpoolTimer
0x18000842b  mov     ecx, ebx; dwErrCode
0x18000842d  call    cs:__imp_SetLastError
0x180008433  mov     qword ptr [rdi+38h], 0
0x18000843b  mov     rbx, [rdi+100h]
0x180008442  mov     qword ptr [rdi+100h], 0
0x18000844d  test    rbx, rbx
0x180008450  jz      short loc_180008466
0x180008452  call    cs:__imp_GetProcessHeap
0x180008458  mov     rcx, rax; hHeap
0x18000845b  mov     r8, rbx; lpMem
0x18000845e  xor     edx, edx; dwFlags
0x180008460  call    cs:__imp_HeapFree
0x180008466  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000846d  test    r8, r8
0x180008470  jz      short loc_18000848A
0x180008472  mov     rdx, cs:qword_180019098; SRWLock
0x180008479  test    rdx, rdx
0x18000847c  jz      short loc_18000848A
0x18000847e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008485  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000848a  lea     rbx, [rdi+98h]
0x180008491  mov     rsi, [rbx+40h]
0x180008495  mov     qword ptr [rbx+40h], 0
0x18000849d  test    rsi, rsi
0x1800084a0  jz      short loc_1800084B6
0x1800084a2  call    cs:__imp_GetProcessHeap
0x1800084a8  mov     rcx, rax; hHeap
0x1800084ab  mov     r8, rsi; lpMem
0x1800084ae  xor     edx, edx; dwFlags
0x1800084b0  call    cs:__imp_HeapFree
0x1800084b6  mov     rcx, rbx; lpCriticalSection
0x1800084b9  call    cs:__imp_DeleteCriticalSection
0x1800084bf  lea     rcx, [rdi+90h]
0x1800084c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800084cb  mov     rsi, [rdi+88h]
0x1800084d2  mov     qword ptr [rdi+88h], 0
0x1800084dd  test    rsi, rsi
0x1800084e0  jz      short loc_1800084F6
0x1800084e2  call    cs:__imp_GetProcessHeap
0x1800084e8  mov     rcx, rax; hHeap
0x1800084eb  mov     r8, rsi; lpMem
0x1800084ee  xor     edx, edx; dwFlags
0x1800084f0  call    cs:__imp_HeapFree
0x1800084f6  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800084fa  call    cs:__imp_DeleteCriticalSection
0x180008500  mov     rbx, [rdi+38h]
0x180008504  test    rbx, rbx
0x180008507  jz      short loc_180008531
0x180008509  xor     r9d, r9d; msWindowLength
0x18000850c  xor     r8d, r8d; msPeriod
0x18000850f  xor     edx, edx; pftDueTime
0x180008511  mov     rcx, rbx; pti
0x180008514  call    cs:__imp_SetThreadpoolTimer
0x18000851a  mov     edx, 1; fCancelPendingCallbacks
0x18000851f  mov     rcx, rbx; pti
0x180008522  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008528  mov     rcx, rbx; pti
0x18000852b  call    cs:__imp_CloseThreadpoolTimer
0x180008531  mov     rbx, [rdi+30h]
0x180008535  test    rbx, rbx
0x180008538  jz      short loc_180008563
0x18000853a  xor     r9d, r9d; msWindowLength
0x18000853d  xor     r8d, r8d; msPeriod
0x180008540  xor     edx, edx; pftDueTime
0x180008542  mov     rcx, rbx; pti
0x180008545  call    cs:__imp_SetThreadpoolTimer
0x18000854b  mov     edx, 1; fCancelPendingCallbacks
0x180008550  mov     rcx, rbx; pti
0x180008553  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008559  mov     rcx, rbx; pti
0x18000855c  call    cs:__imp_CloseThreadpoolTimer
0x180008562  nop
0x180008563  mov     rcx, [rdi+10h]; lpMem
0x180008567  test    rcx, rcx
0x18000856a  jz      short loc_180008572
0x18000856c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008571  nop
0x180008572  mov     rbx, [rsp+28h+arg_0]
0x180008577  mov     rsi, [rsp+28h+arg_8]
0x18000857c  add     rsp, 20h
0x180008580  pop     rdi
0x180008581  retn
```
