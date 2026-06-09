# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000a020`
- end: `0x18000a20e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180069c40`

## callees

- `0x180009d38`
- `0x18000a020`
- `0x18000cc8c`
- `0x18000db28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a12e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a16e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a12e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a16e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a13c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a17c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a13c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a03e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a03e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a087`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a070`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a070`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a145`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a186`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a145`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a186`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a068`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a0b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a068`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a0b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a1e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a051`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a09a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a051`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a09a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a05f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a0a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a1ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a1df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a05f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a0a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a1ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a1df`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  if ( v8 && qword_18008F3B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18008F3B8[25], qword_18008F3B8, v8);
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
0x18000a020  mov     [rsp+arg_0], rbx
0x18000a025  mov     [rsp+arg_8], rsi
0x18000a02a  push    rdi
0x18000a02b  sub     rsp, 20h
0x18000a02f  mov     rdi, rcx
0x18000a032  mov     byte ptr [rcx], 0
0x18000a035  mov     rsi, [rcx+30h]
0x18000a039  test    rsi, rsi
0x18000a03c  jz      short loc_18000A076
0x18000a03e  call    cs:__imp_GetLastError
0x18000a044  mov     ebx, eax
0x18000a046  xor     r9d, r9d; msWindowLength
0x18000a049  xor     r8d, r8d; msPeriod
0x18000a04c  xor     edx, edx; pftDueTime
0x18000a04e  mov     rcx, rsi; pti
0x18000a051  call    cs:__imp_SetThreadpoolTimer
0x18000a057  mov     edx, 1; fCancelPendingCallbacks
0x18000a05c  mov     rcx, rsi; pti
0x18000a05f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a065  mov     rcx, rsi; pti
0x18000a068  call    cs:__imp_CloseThreadpoolTimer
0x18000a06e  mov     ecx, ebx; dwErrCode
0x18000a070  call    cs:__imp_SetLastError
0x18000a076  mov     qword ptr [rdi+30h], 0
0x18000a07e  mov     rsi, [rdi+38h]
0x18000a082  test    rsi, rsi
0x18000a085  jz      short loc_18000A0BF
0x18000a087  call    cs:__imp_GetLastError
0x18000a08d  mov     ebx, eax
0x18000a08f  xor     r9d, r9d; msWindowLength
0x18000a092  xor     r8d, r8d; msPeriod
0x18000a095  xor     edx, edx; pftDueTime
0x18000a097  mov     rcx, rsi; pti
0x18000a09a  call    cs:__imp_SetThreadpoolTimer
0x18000a0a0  mov     edx, 1; fCancelPendingCallbacks
0x18000a0a5  mov     rcx, rsi; pti
0x18000a0a8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a0ae  mov     rcx, rsi; pti
0x18000a0b1  call    cs:__imp_CloseThreadpoolTimer
0x18000a0b7  mov     ecx, ebx; dwErrCode
0x18000a0b9  call    cs:__imp_SetLastError
0x18000a0bf  mov     qword ptr [rdi+38h], 0
0x18000a0c7  mov     rbx, [rdi+100h]
0x18000a0ce  mov     qword ptr [rdi+100h], 0
0x18000a0d9  test    rbx, rbx
0x18000a0dc  jz      short loc_18000A0F2
0x18000a0de  call    cs:__imp_GetProcessHeap
0x18000a0e4  mov     rcx, rax; hHeap
0x18000a0e7  mov     r8, rbx; lpMem
0x18000a0ea  xor     edx, edx; dwFlags
0x18000a0ec  call    cs:__imp_HeapFree
0x18000a0f2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000a0f9  test    r8, r8
0x18000a0fc  jz      short loc_18000A116
0x18000a0fe  mov     rdx, cs:qword_18008F3B8; SRWLock
0x18000a105  test    rdx, rdx
0x18000a108  jz      short loc_18000A116
0x18000a10a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a111  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000a116  lea     rbx, [rdi+98h]
0x18000a11d  mov     rsi, [rbx+40h]
0x18000a121  mov     qword ptr [rbx+40h], 0
0x18000a129  test    rsi, rsi
0x18000a12c  jz      short loc_18000A142
0x18000a12e  call    cs:__imp_GetProcessHeap
0x18000a134  mov     rcx, rax; hHeap
0x18000a137  mov     r8, rsi; lpMem
0x18000a13a  xor     edx, edx; dwFlags
0x18000a13c  call    cs:__imp_HeapFree
0x18000a142  mov     rcx, rbx; lpCriticalSection
0x18000a145  call    cs:__imp_DeleteCriticalSection
0x18000a14b  lea     rcx, [rdi+90h]
0x18000a152  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000a157  mov     rsi, [rdi+88h]
0x18000a15e  mov     qword ptr [rdi+88h], 0
0x18000a169  test    rsi, rsi
0x18000a16c  jz      short loc_18000A182
0x18000a16e  call    cs:__imp_GetProcessHeap
0x18000a174  mov     rcx, rax; hHeap
0x18000a177  mov     r8, rsi; lpMem
0x18000a17a  xor     edx, edx; dwFlags
0x18000a17c  call    cs:__imp_HeapFree
0x18000a182  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000a186  call    cs:__imp_DeleteCriticalSection
0x18000a18c  mov     rbx, [rdi+38h]
0x18000a190  test    rbx, rbx
0x18000a193  jz      short loc_18000A1BD
0x18000a195  xor     r9d, r9d; msWindowLength
0x18000a198  xor     r8d, r8d; msPeriod
0x18000a19b  xor     edx, edx; pftDueTime
0x18000a19d  mov     rcx, rbx; pti
0x18000a1a0  call    cs:__imp_SetThreadpoolTimer
0x18000a1a6  mov     edx, 1; fCancelPendingCallbacks
0x18000a1ab  mov     rcx, rbx; pti
0x18000a1ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a1b4  mov     rcx, rbx; pti
0x18000a1b7  call    cs:__imp_CloseThreadpoolTimer
0x18000a1bd  mov     rbx, [rdi+30h]
0x18000a1c1  test    rbx, rbx
0x18000a1c4  jz      short loc_18000A1EF
0x18000a1c6  xor     r9d, r9d; msWindowLength
0x18000a1c9  xor     r8d, r8d; msPeriod
0x18000a1cc  xor     edx, edx; pftDueTime
0x18000a1ce  mov     rcx, rbx; pti
0x18000a1d1  call    cs:__imp_SetThreadpoolTimer
0x18000a1d7  mov     edx, 1; fCancelPendingCallbacks
0x18000a1dc  mov     rcx, rbx; pti
0x18000a1df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a1e5  mov     rcx, rbx; pti
0x18000a1e8  call    cs:__imp_CloseThreadpoolTimer
0x18000a1ee  nop
0x18000a1ef  mov     rcx, [rdi+10h]; lpMem
0x18000a1f3  test    rcx, rcx
0x18000a1f6  jz      short loc_18000A1FE
0x18000a1f8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000a1fd  nop
0x18000a1fe  mov     rbx, [rsp+28h+arg_0]
0x18000a203  mov     rsi, [rsp+28h+arg_8]
0x18000a208  add     rsp, 20h
0x18000a20c  pop     rdi
0x18000a20d  retn
```
