# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140008b0c`
- end: `0x140008cfa`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012720`

## callees

- `0x140008868`
- `0x140008b0c`
- `0x14000d0ac`
- `0x14000e320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008b5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008ba5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008b5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008ba5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008c31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008c72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008c31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008c72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008bd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008bd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008c68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008c5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008c8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008cbd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008b86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008c8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008cbd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008c9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008ccb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008b94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008c9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008ccb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008ca3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008cd4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008b9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008ca3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008cd4`

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
  if ( v8 && qword_14001B178 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14001B178[25], qword_14001B178, v8);
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
0x140008b0c  mov     [rsp+arg_0], rbx
0x140008b11  mov     [rsp+arg_8], rsi
0x140008b16  push    rdi
0x140008b17  sub     rsp, 20h
0x140008b1b  mov     rdi, rcx
0x140008b1e  mov     byte ptr [rcx], 0
0x140008b21  mov     rsi, [rcx+30h]
0x140008b25  test    rsi, rsi
0x140008b28  jz      short loc_140008B62
0x140008b2a  call    cs:__imp_GetLastError
0x140008b30  mov     ebx, eax
0x140008b32  xor     r9d, r9d; msWindowLength
0x140008b35  xor     r8d, r8d; msPeriod
0x140008b38  xor     edx, edx; pftDueTime
0x140008b3a  mov     rcx, rsi; pti
0x140008b3d  call    cs:__imp_SetThreadpoolTimer
0x140008b43  mov     edx, 1; fCancelPendingCallbacks
0x140008b48  mov     rcx, rsi; pti
0x140008b4b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008b51  mov     rcx, rsi; pti
0x140008b54  call    cs:__imp_CloseThreadpoolTimer
0x140008b5a  mov     ecx, ebx; dwErrCode
0x140008b5c  call    cs:__imp_SetLastError
0x140008b62  mov     qword ptr [rdi+30h], 0
0x140008b6a  mov     rsi, [rdi+38h]
0x140008b6e  test    rsi, rsi
0x140008b71  jz      short loc_140008BAB
0x140008b73  call    cs:__imp_GetLastError
0x140008b79  mov     ebx, eax
0x140008b7b  xor     r9d, r9d; msWindowLength
0x140008b7e  xor     r8d, r8d; msPeriod
0x140008b81  xor     edx, edx; pftDueTime
0x140008b83  mov     rcx, rsi; pti
0x140008b86  call    cs:__imp_SetThreadpoolTimer
0x140008b8c  mov     edx, 1; fCancelPendingCallbacks
0x140008b91  mov     rcx, rsi; pti
0x140008b94  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008b9a  mov     rcx, rsi; pti
0x140008b9d  call    cs:__imp_CloseThreadpoolTimer
0x140008ba3  mov     ecx, ebx; dwErrCode
0x140008ba5  call    cs:__imp_SetLastError
0x140008bab  mov     qword ptr [rdi+38h], 0
0x140008bb3  mov     rbx, [rdi+100h]
0x140008bba  mov     qword ptr [rdi+100h], 0
0x140008bc5  test    rbx, rbx
0x140008bc8  jz      short loc_140008BDE
0x140008bca  call    cs:__imp_GetProcessHeap
0x140008bd0  mov     rcx, rax; hHeap
0x140008bd3  mov     r8, rbx; lpMem
0x140008bd6  xor     edx, edx; dwFlags
0x140008bd8  call    cs:__imp_HeapFree
0x140008bde  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140008be5  test    r8, r8
0x140008be8  jz      short loc_140008C02
0x140008bea  mov     rdx, cs:qword_14001B178; SRWLock
0x140008bf1  test    rdx, rdx
0x140008bf4  jz      short loc_140008C02
0x140008bf6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140008bfd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140008c02  lea     rbx, [rdi+98h]
0x140008c09  mov     rsi, [rbx+40h]
0x140008c0d  mov     qword ptr [rbx+40h], 0
0x140008c15  test    rsi, rsi
0x140008c18  jz      short loc_140008C2E
0x140008c1a  call    cs:__imp_GetProcessHeap
0x140008c20  mov     rcx, rax; hHeap
0x140008c23  mov     r8, rsi; lpMem
0x140008c26  xor     edx, edx; dwFlags
0x140008c28  call    cs:__imp_HeapFree
0x140008c2e  mov     rcx, rbx; lpCriticalSection
0x140008c31  call    cs:__imp_DeleteCriticalSection
0x140008c37  lea     rcx, [rdi+90h]
0x140008c3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140008c43  mov     rsi, [rdi+88h]
0x140008c4a  mov     qword ptr [rdi+88h], 0
0x140008c55  test    rsi, rsi
0x140008c58  jz      short loc_140008C6E
0x140008c5a  call    cs:__imp_GetProcessHeap
0x140008c60  mov     rcx, rax; hHeap
0x140008c63  mov     r8, rsi; lpMem
0x140008c66  xor     edx, edx; dwFlags
0x140008c68  call    cs:__imp_HeapFree
0x140008c6e  lea     rcx, [rdi+48h]; lpCriticalSection
0x140008c72  call    cs:__imp_DeleteCriticalSection
0x140008c78  mov     rbx, [rdi+38h]
0x140008c7c  test    rbx, rbx
0x140008c7f  jz      short loc_140008CA9
0x140008c81  xor     r9d, r9d; msWindowLength
0x140008c84  xor     r8d, r8d; msPeriod
0x140008c87  xor     edx, edx; pftDueTime
0x140008c89  mov     rcx, rbx; pti
0x140008c8c  call    cs:__imp_SetThreadpoolTimer
0x140008c92  mov     edx, 1; fCancelPendingCallbacks
0x140008c97  mov     rcx, rbx; pti
0x140008c9a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008ca0  mov     rcx, rbx; pti
0x140008ca3  call    cs:__imp_CloseThreadpoolTimer
0x140008ca9  mov     rbx, [rdi+30h]
0x140008cad  test    rbx, rbx
0x140008cb0  jz      short loc_140008CDB
0x140008cb2  xor     r9d, r9d; msWindowLength
0x140008cb5  xor     r8d, r8d; msPeriod
0x140008cb8  xor     edx, edx; pftDueTime
0x140008cba  mov     rcx, rbx; pti
0x140008cbd  call    cs:__imp_SetThreadpoolTimer
0x140008cc3  mov     edx, 1; fCancelPendingCallbacks
0x140008cc8  mov     rcx, rbx; pti
0x140008ccb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008cd1  mov     rcx, rbx; pti
0x140008cd4  call    cs:__imp_CloseThreadpoolTimer
0x140008cda  nop
0x140008cdb  mov     rcx, [rdi+10h]; lpMem
0x140008cdf  test    rcx, rcx
0x140008ce2  jz      short loc_140008CEA
0x140008ce4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140008ce9  nop
0x140008cea  mov     rbx, [rsp+28h+arg_0]
0x140008cef  mov     rsi, [rsp+28h+arg_8]
0x140008cf4  add     rsp, 20h
0x140008cf8  pop     rdi
0x140008cf9  retn
```
