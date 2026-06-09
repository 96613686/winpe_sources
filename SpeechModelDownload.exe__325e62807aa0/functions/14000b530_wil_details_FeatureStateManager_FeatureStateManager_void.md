# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000b530`
- end: `0x14000b71e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001c5f0`

## callees

- `0x14000b1e8`
- `0x14000b530`
- `0x140011d0c`
- `0x14001256c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000b655`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000b696`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000b655`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000b696`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b5ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b63e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b67e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b5ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b63e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b67e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b5fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b64c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b68c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b5fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b64c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b68c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b597`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b580`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b5c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b580`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b5c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b561`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b5aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b6b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b6e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b561`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b5aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b6b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b6e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b578`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b5c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b6c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b6f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b578`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b5c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b6c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b6f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b56f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b5b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b6be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b6ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b56f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b5b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b6be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b6ef`

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
  if ( v8 && qword_140030150 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140030150[25], qword_140030150, v8);
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
0x14000b530  mov     [rsp+arg_0], rbx
0x14000b535  mov     [rsp+arg_8], rsi
0x14000b53a  push    rdi
0x14000b53b  sub     rsp, 20h
0x14000b53f  mov     rdi, rcx
0x14000b542  mov     byte ptr [rcx], 0
0x14000b545  mov     rsi, [rcx+30h]
0x14000b549  test    rsi, rsi
0x14000b54c  jz      short loc_14000B586
0x14000b54e  call    cs:__imp_GetLastError
0x14000b554  mov     ebx, eax
0x14000b556  xor     r9d, r9d; msWindowLength
0x14000b559  xor     r8d, r8d; msPeriod
0x14000b55c  xor     edx, edx; pftDueTime
0x14000b55e  mov     rcx, rsi; pti
0x14000b561  call    cs:__imp_SetThreadpoolTimer
0x14000b567  mov     edx, 1; fCancelPendingCallbacks
0x14000b56c  mov     rcx, rsi; pti
0x14000b56f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b575  mov     rcx, rsi; pti
0x14000b578  call    cs:__imp_CloseThreadpoolTimer
0x14000b57e  mov     ecx, ebx; dwErrCode
0x14000b580  call    cs:__imp_SetLastError
0x14000b586  mov     qword ptr [rdi+30h], 0
0x14000b58e  mov     rsi, [rdi+38h]
0x14000b592  test    rsi, rsi
0x14000b595  jz      short loc_14000B5CF
0x14000b597  call    cs:__imp_GetLastError
0x14000b59d  mov     ebx, eax
0x14000b59f  xor     r9d, r9d; msWindowLength
0x14000b5a2  xor     r8d, r8d; msPeriod
0x14000b5a5  xor     edx, edx; pftDueTime
0x14000b5a7  mov     rcx, rsi; pti
0x14000b5aa  call    cs:__imp_SetThreadpoolTimer
0x14000b5b0  mov     edx, 1; fCancelPendingCallbacks
0x14000b5b5  mov     rcx, rsi; pti
0x14000b5b8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b5be  mov     rcx, rsi; pti
0x14000b5c1  call    cs:__imp_CloseThreadpoolTimer
0x14000b5c7  mov     ecx, ebx; dwErrCode
0x14000b5c9  call    cs:__imp_SetLastError
0x14000b5cf  mov     qword ptr [rdi+38h], 0
0x14000b5d7  mov     rbx, [rdi+100h]
0x14000b5de  mov     qword ptr [rdi+100h], 0
0x14000b5e9  test    rbx, rbx
0x14000b5ec  jz      short loc_14000B602
0x14000b5ee  call    cs:__imp_GetProcessHeap
0x14000b5f4  mov     rcx, rax; hHeap
0x14000b5f7  mov     r8, rbx; lpMem
0x14000b5fa  xor     edx, edx; dwFlags
0x14000b5fc  call    cs:__imp_HeapFree
0x14000b602  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14000b609  test    r8, r8
0x14000b60c  jz      short loc_14000B626
0x14000b60e  mov     rdx, cs:qword_140030150; SRWLock
0x14000b615  test    rdx, rdx
0x14000b618  jz      short loc_14000B626
0x14000b61a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000b621  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000b626  lea     rbx, [rdi+98h]
0x14000b62d  mov     rsi, [rbx+40h]
0x14000b631  mov     qword ptr [rbx+40h], 0
0x14000b639  test    rsi, rsi
0x14000b63c  jz      short loc_14000B652
0x14000b63e  call    cs:__imp_GetProcessHeap
0x14000b644  mov     rcx, rax; hHeap
0x14000b647  mov     r8, rsi; lpMem
0x14000b64a  xor     edx, edx; dwFlags
0x14000b64c  call    cs:__imp_HeapFree
0x14000b652  mov     rcx, rbx; lpCriticalSection
0x14000b655  call    cs:__imp_DeleteCriticalSection
0x14000b65b  lea     rcx, [rdi+90h]
0x14000b662  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000b667  mov     rsi, [rdi+88h]
0x14000b66e  mov     qword ptr [rdi+88h], 0
0x14000b679  test    rsi, rsi
0x14000b67c  jz      short loc_14000B692
0x14000b67e  call    cs:__imp_GetProcessHeap
0x14000b684  mov     rcx, rax; hHeap
0x14000b687  mov     r8, rsi; lpMem
0x14000b68a  xor     edx, edx; dwFlags
0x14000b68c  call    cs:__imp_HeapFree
0x14000b692  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000b696  call    cs:__imp_DeleteCriticalSection
0x14000b69c  mov     rbx, [rdi+38h]
0x14000b6a0  test    rbx, rbx
0x14000b6a3  jz      short loc_14000B6CD
0x14000b6a5  xor     r9d, r9d; msWindowLength
0x14000b6a8  xor     r8d, r8d; msPeriod
0x14000b6ab  xor     edx, edx; pftDueTime
0x14000b6ad  mov     rcx, rbx; pti
0x14000b6b0  call    cs:__imp_SetThreadpoolTimer
0x14000b6b6  mov     edx, 1; fCancelPendingCallbacks
0x14000b6bb  mov     rcx, rbx; pti
0x14000b6be  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b6c4  mov     rcx, rbx; pti
0x14000b6c7  call    cs:__imp_CloseThreadpoolTimer
0x14000b6cd  mov     rbx, [rdi+30h]
0x14000b6d1  test    rbx, rbx
0x14000b6d4  jz      short loc_14000B6FF
0x14000b6d6  xor     r9d, r9d; msWindowLength
0x14000b6d9  xor     r8d, r8d; msPeriod
0x14000b6dc  xor     edx, edx; pftDueTime
0x14000b6de  mov     rcx, rbx; pti
0x14000b6e1  call    cs:__imp_SetThreadpoolTimer
0x14000b6e7  mov     edx, 1; fCancelPendingCallbacks
0x14000b6ec  mov     rcx, rbx; pti
0x14000b6ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b6f5  mov     rcx, rbx; pti
0x14000b6f8  call    cs:__imp_CloseThreadpoolTimer
0x14000b6fe  nop
0x14000b6ff  mov     rcx, [rdi+10h]; lpMem
0x14000b703  test    rcx, rcx
0x14000b706  jz      short loc_14000B70E
0x14000b708  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000b70d  nop
0x14000b70e  mov     rbx, [rsp+28h+arg_0]
0x14000b713  mov     rsi, [rsp+28h+arg_8]
0x14000b718  add     rsp, 20h
0x14000b71c  pop     rdi
0x14000b71d  retn
```
