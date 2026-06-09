# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000534c`
- end: `0x18000553a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ce10`

## callees

- `0x180005208`
- `0x18000534c`
- `0x18000a190`
- `0x18000b610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005418`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000540a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000545a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000549a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000540a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000545a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000549a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000536a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000536a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000539c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000539c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005471`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800054b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005471`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800054b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000538b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800053d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800054da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000550b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000538b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800053d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800054da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000550b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000537d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800053c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000537d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800053c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005394`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800053dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800054e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005514`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005394`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800053dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800054e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005514`

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
  if ( v8 && qword_180014028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180014028[25], qword_180014028, v8);
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
0x18000534c  mov     [rsp+arg_0], rbx
0x180005351  mov     [rsp+arg_8], rsi
0x180005356  push    rdi
0x180005357  sub     rsp, 20h
0x18000535b  mov     rdi, rcx
0x18000535e  mov     byte ptr [rcx], 0
0x180005361  mov     rsi, [rcx+30h]
0x180005365  test    rsi, rsi
0x180005368  jz      short loc_1800053A2
0x18000536a  call    cs:__imp_GetLastError
0x180005370  mov     ebx, eax
0x180005372  xor     r9d, r9d; msWindowLength
0x180005375  xor     r8d, r8d; msPeriod
0x180005378  xor     edx, edx; pftDueTime
0x18000537a  mov     rcx, rsi; pti
0x18000537d  call    cs:__imp_SetThreadpoolTimer
0x180005383  mov     edx, 1; fCancelPendingCallbacks
0x180005388  mov     rcx, rsi; pti
0x18000538b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005391  mov     rcx, rsi; pti
0x180005394  call    cs:__imp_CloseThreadpoolTimer
0x18000539a  mov     ecx, ebx; dwErrCode
0x18000539c  call    cs:__imp_SetLastError
0x1800053a2  mov     qword ptr [rdi+30h], 0
0x1800053aa  mov     rsi, [rdi+38h]
0x1800053ae  test    rsi, rsi
0x1800053b1  jz      short loc_1800053EB
0x1800053b3  call    cs:__imp_GetLastError
0x1800053b9  mov     ebx, eax
0x1800053bb  xor     r9d, r9d; msWindowLength
0x1800053be  xor     r8d, r8d; msPeriod
0x1800053c1  xor     edx, edx; pftDueTime
0x1800053c3  mov     rcx, rsi; pti
0x1800053c6  call    cs:__imp_SetThreadpoolTimer
0x1800053cc  mov     edx, 1; fCancelPendingCallbacks
0x1800053d1  mov     rcx, rsi; pti
0x1800053d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800053da  mov     rcx, rsi; pti
0x1800053dd  call    cs:__imp_CloseThreadpoolTimer
0x1800053e3  mov     ecx, ebx; dwErrCode
0x1800053e5  call    cs:__imp_SetLastError
0x1800053eb  mov     qword ptr [rdi+38h], 0
0x1800053f3  mov     rbx, [rdi+100h]
0x1800053fa  mov     qword ptr [rdi+100h], 0
0x180005405  test    rbx, rbx
0x180005408  jz      short loc_18000541E
0x18000540a  call    cs:__imp_GetProcessHeap
0x180005410  mov     rcx, rax; hHeap
0x180005413  mov     r8, rbx; lpMem
0x180005416  xor     edx, edx; dwFlags
0x180005418  call    cs:__imp_HeapFree
0x18000541e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180005425  test    r8, r8
0x180005428  jz      short loc_180005442
0x18000542a  mov     rdx, cs:qword_180014028; SRWLock
0x180005431  test    rdx, rdx
0x180005434  jz      short loc_180005442
0x180005436  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000543d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180005442  lea     rbx, [rdi+98h]
0x180005449  mov     rsi, [rbx+40h]
0x18000544d  mov     qword ptr [rbx+40h], 0
0x180005455  test    rsi, rsi
0x180005458  jz      short loc_18000546E
0x18000545a  call    cs:__imp_GetProcessHeap
0x180005460  mov     rcx, rax; hHeap
0x180005463  mov     r8, rsi; lpMem
0x180005466  xor     edx, edx; dwFlags
0x180005468  call    cs:__imp_HeapFree
0x18000546e  mov     rcx, rbx; lpCriticalSection
0x180005471  call    cs:__imp_DeleteCriticalSection
0x180005477  lea     rcx, [rdi+90h]
0x18000547e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005483  mov     rsi, [rdi+88h]
0x18000548a  mov     qword ptr [rdi+88h], 0
0x180005495  test    rsi, rsi
0x180005498  jz      short loc_1800054AE
0x18000549a  call    cs:__imp_GetProcessHeap
0x1800054a0  mov     rcx, rax; hHeap
0x1800054a3  mov     r8, rsi; lpMem
0x1800054a6  xor     edx, edx; dwFlags
0x1800054a8  call    cs:__imp_HeapFree
0x1800054ae  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800054b2  call    cs:__imp_DeleteCriticalSection
0x1800054b8  mov     rbx, [rdi+38h]
0x1800054bc  test    rbx, rbx
0x1800054bf  jz      short loc_1800054E9
0x1800054c1  xor     r9d, r9d; msWindowLength
0x1800054c4  xor     r8d, r8d; msPeriod
0x1800054c7  xor     edx, edx; pftDueTime
0x1800054c9  mov     rcx, rbx; pti
0x1800054cc  call    cs:__imp_SetThreadpoolTimer
0x1800054d2  mov     edx, 1; fCancelPendingCallbacks
0x1800054d7  mov     rcx, rbx; pti
0x1800054da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800054e0  mov     rcx, rbx; pti
0x1800054e3  call    cs:__imp_CloseThreadpoolTimer
0x1800054e9  mov     rbx, [rdi+30h]
0x1800054ed  test    rbx, rbx
0x1800054f0  jz      short loc_18000551B
0x1800054f2  xor     r9d, r9d; msWindowLength
0x1800054f5  xor     r8d, r8d; msPeriod
0x1800054f8  xor     edx, edx; pftDueTime
0x1800054fa  mov     rcx, rbx; pti
0x1800054fd  call    cs:__imp_SetThreadpoolTimer
0x180005503  mov     edx, 1; fCancelPendingCallbacks
0x180005508  mov     rcx, rbx; pti
0x18000550b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005511  mov     rcx, rbx; pti
0x180005514  call    cs:__imp_CloseThreadpoolTimer
0x18000551a  nop
0x18000551b  mov     rcx, [rdi+10h]; lpMem
0x18000551f  test    rcx, rcx
0x180005522  jz      short loc_18000552A
0x180005524  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180005529  nop
0x18000552a  mov     rbx, [rsp+28h+arg_0]
0x18000552f  mov     rsi, [rsp+28h+arg_8]
0x180005534  add     rsp, 20h
0x180005538  pop     rdi
0x180005539  retn
```
