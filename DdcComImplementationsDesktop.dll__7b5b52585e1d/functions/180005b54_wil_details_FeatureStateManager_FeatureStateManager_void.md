# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180005b54`
- end: `0x180005d42`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bef0`

## callees

- `0x180005a10`
- `0x180005b54`
- `0x180009300`
- `0x18000a590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ba4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ba4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005cb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ca2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ca2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005bce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005cd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005b85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005bce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005cd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005d05`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005b93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005bdc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ce2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005d13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005b93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005bdc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ce2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005d13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005b9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005be5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005ceb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005d1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005b9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005be5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005ceb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005d1c`

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
  if ( v8 && qword_1800130A8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800130A8[25], qword_1800130A8, v8);
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
0x180005b54  mov     [rsp+arg_0], rbx
0x180005b59  mov     [rsp+arg_8], rsi
0x180005b5e  push    rdi
0x180005b5f  sub     rsp, 20h
0x180005b63  mov     rdi, rcx
0x180005b66  mov     byte ptr [rcx], 0
0x180005b69  mov     rsi, [rcx+30h]
0x180005b6d  test    rsi, rsi
0x180005b70  jz      short loc_180005BAA
0x180005b72  call    cs:__imp_GetLastError
0x180005b78  mov     ebx, eax
0x180005b7a  xor     r9d, r9d; msWindowLength
0x180005b7d  xor     r8d, r8d; msPeriod
0x180005b80  xor     edx, edx; pftDueTime
0x180005b82  mov     rcx, rsi; pti
0x180005b85  call    cs:__imp_SetThreadpoolTimer
0x180005b8b  mov     edx, 1; fCancelPendingCallbacks
0x180005b90  mov     rcx, rsi; pti
0x180005b93  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005b99  mov     rcx, rsi; pti
0x180005b9c  call    cs:__imp_CloseThreadpoolTimer
0x180005ba2  mov     ecx, ebx; dwErrCode
0x180005ba4  call    cs:__imp_SetLastError
0x180005baa  mov     qword ptr [rdi+30h], 0
0x180005bb2  mov     rsi, [rdi+38h]
0x180005bb6  test    rsi, rsi
0x180005bb9  jz      short loc_180005BF3
0x180005bbb  call    cs:__imp_GetLastError
0x180005bc1  mov     ebx, eax
0x180005bc3  xor     r9d, r9d; msWindowLength
0x180005bc6  xor     r8d, r8d; msPeriod
0x180005bc9  xor     edx, edx; pftDueTime
0x180005bcb  mov     rcx, rsi; pti
0x180005bce  call    cs:__imp_SetThreadpoolTimer
0x180005bd4  mov     edx, 1; fCancelPendingCallbacks
0x180005bd9  mov     rcx, rsi; pti
0x180005bdc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005be2  mov     rcx, rsi; pti
0x180005be5  call    cs:__imp_CloseThreadpoolTimer
0x180005beb  mov     ecx, ebx; dwErrCode
0x180005bed  call    cs:__imp_SetLastError
0x180005bf3  mov     qword ptr [rdi+38h], 0
0x180005bfb  mov     rbx, [rdi+100h]
0x180005c02  mov     qword ptr [rdi+100h], 0
0x180005c0d  test    rbx, rbx
0x180005c10  jz      short loc_180005C26
0x180005c12  call    cs:__imp_GetProcessHeap
0x180005c18  mov     rcx, rax; hHeap
0x180005c1b  mov     r8, rbx; lpMem
0x180005c1e  xor     edx, edx; dwFlags
0x180005c20  call    cs:__imp_HeapFree
0x180005c26  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180005c2d  test    r8, r8
0x180005c30  jz      short loc_180005C4A
0x180005c32  mov     rdx, cs:qword_1800130A8; SRWLock
0x180005c39  test    rdx, rdx
0x180005c3c  jz      short loc_180005C4A
0x180005c3e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180005c45  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005c4a  lea     rbx, [rdi+98h]
0x180005c51  mov     rsi, [rbx+40h]
0x180005c55  mov     qword ptr [rbx+40h], 0
0x180005c5d  test    rsi, rsi
0x180005c60  jz      short loc_180005C76
0x180005c62  call    cs:__imp_GetProcessHeap
0x180005c68  mov     rcx, rax; hHeap
0x180005c6b  mov     r8, rsi; lpMem
0x180005c6e  xor     edx, edx; dwFlags
0x180005c70  call    cs:__imp_HeapFree
0x180005c76  mov     rcx, rbx; lpCriticalSection
0x180005c79  call    cs:__imp_DeleteCriticalSection
0x180005c7f  lea     rcx, [rdi+90h]
0x180005c86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005c8b  mov     rsi, [rdi+88h]
0x180005c92  mov     qword ptr [rdi+88h], 0
0x180005c9d  test    rsi, rsi
0x180005ca0  jz      short loc_180005CB6
0x180005ca2  call    cs:__imp_GetProcessHeap
0x180005ca8  mov     rcx, rax; hHeap
0x180005cab  mov     r8, rsi; lpMem
0x180005cae  xor     edx, edx; dwFlags
0x180005cb0  call    cs:__imp_HeapFree
0x180005cb6  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005cba  call    cs:__imp_DeleteCriticalSection
0x180005cc0  mov     rbx, [rdi+38h]
0x180005cc4  test    rbx, rbx
0x180005cc7  jz      short loc_180005CF1
0x180005cc9  xor     r9d, r9d; msWindowLength
0x180005ccc  xor     r8d, r8d; msPeriod
0x180005ccf  xor     edx, edx; pftDueTime
0x180005cd1  mov     rcx, rbx; pti
0x180005cd4  call    cs:__imp_SetThreadpoolTimer
0x180005cda  mov     edx, 1; fCancelPendingCallbacks
0x180005cdf  mov     rcx, rbx; pti
0x180005ce2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005ce8  mov     rcx, rbx; pti
0x180005ceb  call    cs:__imp_CloseThreadpoolTimer
0x180005cf1  mov     rbx, [rdi+30h]
0x180005cf5  test    rbx, rbx
0x180005cf8  jz      short loc_180005D23
0x180005cfa  xor     r9d, r9d; msWindowLength
0x180005cfd  xor     r8d, r8d; msPeriod
0x180005d00  xor     edx, edx; pftDueTime
0x180005d02  mov     rcx, rbx; pti
0x180005d05  call    cs:__imp_SetThreadpoolTimer
0x180005d0b  mov     edx, 1; fCancelPendingCallbacks
0x180005d10  mov     rcx, rbx; pti
0x180005d13  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005d19  mov     rcx, rbx; pti
0x180005d1c  call    cs:__imp_CloseThreadpoolTimer
0x180005d22  nop
0x180005d23  mov     rcx, [rdi+10h]; lpMem
0x180005d27  test    rcx, rcx
0x180005d2a  jz      short loc_180005D32
0x180005d2c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180005d31  nop
0x180005d32  mov     rbx, [rsp+28h+arg_0]
0x180005d37  mov     rsi, [rsp+28h+arg_8]
0x180005d3c  add     rsp, 20h
0x180005d40  pop     rdi
0x180005d41  retn
```
