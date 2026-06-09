# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180028274`
- end: `0x180028462`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180036540`

## callees

- `0x180027f68`
- `0x180028274`
- `0x18002d57c`
- `0x18002f47c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800282db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800282c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002830d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800282c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002830d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028399`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800283da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028399`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800283da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800283d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028390`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800283d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800283c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028382`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800283c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800282b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800282fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180028402`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180028433`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800282b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800282fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180028402`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180028433`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800282bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180028305`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002840b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002843c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800282bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180028305`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002840b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002843c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800282a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800282ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800283f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028425`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800282a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800282ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800283f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180028425`

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
  if ( v8 && qword_180046098 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180046098[25], qword_180046098, v8);
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
0x180028274  mov     [rsp+arg_0], rbx
0x180028279  mov     [rsp+arg_8], rsi
0x18002827e  push    rdi
0x18002827f  sub     rsp, 20h
0x180028283  mov     rdi, rcx
0x180028286  mov     byte ptr [rcx], 0
0x180028289  mov     rsi, [rcx+30h]
0x18002828d  test    rsi, rsi
0x180028290  jz      short loc_1800282CA
0x180028292  call    cs:__imp_GetLastError
0x180028298  mov     ebx, eax
0x18002829a  xor     r9d, r9d; msWindowLength
0x18002829d  xor     r8d, r8d; msPeriod
0x1800282a0  xor     edx, edx; pftDueTime
0x1800282a2  mov     rcx, rsi; pti
0x1800282a5  call    cs:__imp_SetThreadpoolTimer
0x1800282ab  mov     edx, 1; fCancelPendingCallbacks
0x1800282b0  mov     rcx, rsi; pti
0x1800282b3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800282b9  mov     rcx, rsi; pti
0x1800282bc  call    cs:__imp_CloseThreadpoolTimer
0x1800282c2  mov     ecx, ebx; dwErrCode
0x1800282c4  call    cs:__imp_SetLastError
0x1800282ca  mov     qword ptr [rdi+30h], 0
0x1800282d2  mov     rsi, [rdi+38h]
0x1800282d6  test    rsi, rsi
0x1800282d9  jz      short loc_180028313
0x1800282db  call    cs:__imp_GetLastError
0x1800282e1  mov     ebx, eax
0x1800282e3  xor     r9d, r9d; msWindowLength
0x1800282e6  xor     r8d, r8d; msPeriod
0x1800282e9  xor     edx, edx; pftDueTime
0x1800282eb  mov     rcx, rsi; pti
0x1800282ee  call    cs:__imp_SetThreadpoolTimer
0x1800282f4  mov     edx, 1; fCancelPendingCallbacks
0x1800282f9  mov     rcx, rsi; pti
0x1800282fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180028302  mov     rcx, rsi; pti
0x180028305  call    cs:__imp_CloseThreadpoolTimer
0x18002830b  mov     ecx, ebx; dwErrCode
0x18002830d  call    cs:__imp_SetLastError
0x180028313  mov     qword ptr [rdi+38h], 0
0x18002831b  mov     rbx, [rdi+100h]
0x180028322  mov     qword ptr [rdi+100h], 0
0x18002832d  test    rbx, rbx
0x180028330  jz      short loc_180028346
0x180028332  call    cs:__imp_GetProcessHeap
0x180028338  mov     rcx, rax; hHeap
0x18002833b  mov     r8, rbx; lpMem
0x18002833e  xor     edx, edx; dwFlags
0x180028340  call    cs:__imp_HeapFree
0x180028346  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18002834d  test    r8, r8
0x180028350  jz      short loc_18002836A
0x180028352  mov     rdx, cs:qword_180046098; SRWLock
0x180028359  test    rdx, rdx
0x18002835c  jz      short loc_18002836A
0x18002835e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180028365  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18002836a  lea     rbx, [rdi+98h]
0x180028371  mov     rsi, [rbx+40h]
0x180028375  mov     qword ptr [rbx+40h], 0
0x18002837d  test    rsi, rsi
0x180028380  jz      short loc_180028396
0x180028382  call    cs:__imp_GetProcessHeap
0x180028388  mov     rcx, rax; hHeap
0x18002838b  mov     r8, rsi; lpMem
0x18002838e  xor     edx, edx; dwFlags
0x180028390  call    cs:__imp_HeapFree
0x180028396  mov     rcx, rbx; lpCriticalSection
0x180028399  call    cs:__imp_DeleteCriticalSection
0x18002839f  lea     rcx, [rdi+90h]
0x1800283a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800283ab  mov     rsi, [rdi+88h]
0x1800283b2  mov     qword ptr [rdi+88h], 0
0x1800283bd  test    rsi, rsi
0x1800283c0  jz      short loc_1800283D6
0x1800283c2  call    cs:__imp_GetProcessHeap
0x1800283c8  mov     rcx, rax; hHeap
0x1800283cb  mov     r8, rsi; lpMem
0x1800283ce  xor     edx, edx; dwFlags
0x1800283d0  call    cs:__imp_HeapFree
0x1800283d6  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800283da  call    cs:__imp_DeleteCriticalSection
0x1800283e0  mov     rbx, [rdi+38h]
0x1800283e4  test    rbx, rbx
0x1800283e7  jz      short loc_180028411
0x1800283e9  xor     r9d, r9d; msWindowLength
0x1800283ec  xor     r8d, r8d; msPeriod
0x1800283ef  xor     edx, edx; pftDueTime
0x1800283f1  mov     rcx, rbx; pti
0x1800283f4  call    cs:__imp_SetThreadpoolTimer
0x1800283fa  mov     edx, 1; fCancelPendingCallbacks
0x1800283ff  mov     rcx, rbx; pti
0x180028402  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180028408  mov     rcx, rbx; pti
0x18002840b  call    cs:__imp_CloseThreadpoolTimer
0x180028411  mov     rbx, [rdi+30h]
0x180028415  test    rbx, rbx
0x180028418  jz      short loc_180028443
0x18002841a  xor     r9d, r9d; msWindowLength
0x18002841d  xor     r8d, r8d; msPeriod
0x180028420  xor     edx, edx; pftDueTime
0x180028422  mov     rcx, rbx; pti
0x180028425  call    cs:__imp_SetThreadpoolTimer
0x18002842b  mov     edx, 1; fCancelPendingCallbacks
0x180028430  mov     rcx, rbx; pti
0x180028433  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180028439  mov     rcx, rbx; pti
0x18002843c  call    cs:__imp_CloseThreadpoolTimer
0x180028442  nop
0x180028443  mov     rcx, [rdi+10h]; lpMem
0x180028447  test    rcx, rcx
0x18002844a  jz      short loc_180028452
0x18002844c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180028451  nop
0x180028452  mov     rbx, [rsp+28h+arg_0]
0x180028457  mov     rsi, [rsp+28h+arg_8]
0x18002845c  add     rsp, 20h
0x180028460  pop     rdi
0x180028461  retn
```
