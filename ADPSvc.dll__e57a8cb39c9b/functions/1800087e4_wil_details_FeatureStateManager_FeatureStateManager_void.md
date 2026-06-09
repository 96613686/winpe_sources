# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800087e4`
- end: `0x1800089d2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800c9630`

## callees

- `0x180008540`
- `0x1800087e4`
- `0x18000a898`
- `0x18000b078`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008909`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000894a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008909`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000894a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008932`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008932`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008900`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008940`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008900`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008834`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000887d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008834`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000887d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000884b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000884b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008815`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000885e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008964`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008995`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008815`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000885e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008964`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008995`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008823`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000886c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008972`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008823`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000886c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008972`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000882c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008875`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000897b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800089ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000882c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008875`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000897b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800089ac`

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
  if ( v8 && qword_18010E5F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18010E5F8[25], qword_18010E5F8, v8);
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
0x1800087e4  mov     [rsp+arg_0], rbx
0x1800087e9  mov     [rsp+arg_8], rsi
0x1800087ee  push    rdi
0x1800087ef  sub     rsp, 20h
0x1800087f3  mov     rdi, rcx
0x1800087f6  mov     byte ptr [rcx], 0
0x1800087f9  mov     rsi, [rcx+30h]
0x1800087fd  test    rsi, rsi
0x180008800  jz      short loc_18000883A
0x180008802  call    cs:__imp_GetLastError
0x180008808  mov     ebx, eax
0x18000880a  xor     r9d, r9d; msWindowLength
0x18000880d  xor     r8d, r8d; msPeriod
0x180008810  xor     edx, edx; pftDueTime
0x180008812  mov     rcx, rsi; pti
0x180008815  call    cs:__imp_SetThreadpoolTimer
0x18000881b  mov     edx, 1; fCancelPendingCallbacks
0x180008820  mov     rcx, rsi; pti
0x180008823  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008829  mov     rcx, rsi; pti
0x18000882c  call    cs:__imp_CloseThreadpoolTimer
0x180008832  mov     ecx, ebx; dwErrCode
0x180008834  call    cs:__imp_SetLastError
0x18000883a  mov     qword ptr [rdi+30h], 0
0x180008842  mov     rsi, [rdi+38h]
0x180008846  test    rsi, rsi
0x180008849  jz      short loc_180008883
0x18000884b  call    cs:__imp_GetLastError
0x180008851  mov     ebx, eax
0x180008853  xor     r9d, r9d; msWindowLength
0x180008856  xor     r8d, r8d; msPeriod
0x180008859  xor     edx, edx; pftDueTime
0x18000885b  mov     rcx, rsi; pti
0x18000885e  call    cs:__imp_SetThreadpoolTimer
0x180008864  mov     edx, 1; fCancelPendingCallbacks
0x180008869  mov     rcx, rsi; pti
0x18000886c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008872  mov     rcx, rsi; pti
0x180008875  call    cs:__imp_CloseThreadpoolTimer
0x18000887b  mov     ecx, ebx; dwErrCode
0x18000887d  call    cs:__imp_SetLastError
0x180008883  mov     qword ptr [rdi+38h], 0
0x18000888b  mov     rbx, [rdi+100h]
0x180008892  mov     qword ptr [rdi+100h], 0
0x18000889d  test    rbx, rbx
0x1800088a0  jz      short loc_1800088B6
0x1800088a2  call    cs:__imp_GetProcessHeap
0x1800088a8  mov     rcx, rax; hHeap
0x1800088ab  mov     r8, rbx; lpMem
0x1800088ae  xor     edx, edx; dwFlags
0x1800088b0  call    cs:__imp_HeapFree
0x1800088b6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800088bd  test    r8, r8
0x1800088c0  jz      short loc_1800088DA
0x1800088c2  mov     rdx, cs:qword_18010E5F8; SRWLock
0x1800088c9  test    rdx, rdx
0x1800088cc  jz      short loc_1800088DA
0x1800088ce  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800088d5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800088da  lea     rbx, [rdi+98h]
0x1800088e1  mov     rsi, [rbx+40h]
0x1800088e5  mov     qword ptr [rbx+40h], 0
0x1800088ed  test    rsi, rsi
0x1800088f0  jz      short loc_180008906
0x1800088f2  call    cs:__imp_GetProcessHeap
0x1800088f8  mov     rcx, rax; hHeap
0x1800088fb  mov     r8, rsi; lpMem
0x1800088fe  xor     edx, edx; dwFlags
0x180008900  call    cs:__imp_HeapFree
0x180008906  mov     rcx, rbx; lpCriticalSection
0x180008909  call    cs:__imp_DeleteCriticalSection
0x18000890f  lea     rcx, [rdi+90h]
0x180008916  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000891b  mov     rsi, [rdi+88h]
0x180008922  mov     qword ptr [rdi+88h], 0
0x18000892d  test    rsi, rsi
0x180008930  jz      short loc_180008946
0x180008932  call    cs:__imp_GetProcessHeap
0x180008938  mov     rcx, rax; hHeap
0x18000893b  mov     r8, rsi; lpMem
0x18000893e  xor     edx, edx; dwFlags
0x180008940  call    cs:__imp_HeapFree
0x180008946  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000894a  call    cs:__imp_DeleteCriticalSection
0x180008950  mov     rbx, [rdi+38h]
0x180008954  test    rbx, rbx
0x180008957  jz      short loc_180008981
0x180008959  xor     r9d, r9d; msWindowLength
0x18000895c  xor     r8d, r8d; msPeriod
0x18000895f  xor     edx, edx; pftDueTime
0x180008961  mov     rcx, rbx; pti
0x180008964  call    cs:__imp_SetThreadpoolTimer
0x18000896a  mov     edx, 1; fCancelPendingCallbacks
0x18000896f  mov     rcx, rbx; pti
0x180008972  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008978  mov     rcx, rbx; pti
0x18000897b  call    cs:__imp_CloseThreadpoolTimer
0x180008981  mov     rbx, [rdi+30h]
0x180008985  test    rbx, rbx
0x180008988  jz      short loc_1800089B3
0x18000898a  xor     r9d, r9d; msWindowLength
0x18000898d  xor     r8d, r8d; msPeriod
0x180008990  xor     edx, edx; pftDueTime
0x180008992  mov     rcx, rbx; pti
0x180008995  call    cs:__imp_SetThreadpoolTimer
0x18000899b  mov     edx, 1; fCancelPendingCallbacks
0x1800089a0  mov     rcx, rbx; pti
0x1800089a3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800089a9  mov     rcx, rbx; pti
0x1800089ac  call    cs:__imp_CloseThreadpoolTimer
0x1800089b2  nop
0x1800089b3  mov     rcx, [rdi+10h]; lpMem
0x1800089b7  test    rcx, rcx
0x1800089ba  jz      short loc_1800089C2
0x1800089bc  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800089c1  nop
0x1800089c2  mov     rbx, [rsp+28h+arg_0]
0x1800089c7  mov     rsi, [rsp+28h+arg_8]
0x1800089cc  add     rsp, 20h
0x1800089d0  pop     rdi
0x1800089d1  retn
```
