# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000781c`
- end: `0x180007a0a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ecf0`

## callees

- `0x1800076d8`
- `0x18000781c`
- `0x180009c34`
- `0x18000a5f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007941`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007982`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007941`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007982`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000792a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000796a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800078da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000792a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000796a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800078e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000783a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000783a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000786c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000786c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007864`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800078ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007864`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800078ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800079e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000785b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800078a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000785b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800078a4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800079db`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000784d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007896`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000799c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000784d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007896`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000799c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079cd`

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
  if ( v8 && qword_180016098 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180016098[25], qword_180016098, v8);
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
0x18000781c  mov     [rsp+arg_0], rbx
0x180007821  mov     [rsp+arg_8], rsi
0x180007826  push    rdi
0x180007827  sub     rsp, 20h
0x18000782b  mov     rdi, rcx
0x18000782e  mov     byte ptr [rcx], 0
0x180007831  mov     rsi, [rcx+30h]
0x180007835  test    rsi, rsi
0x180007838  jz      short loc_180007872
0x18000783a  call    cs:__imp_GetLastError
0x180007840  mov     ebx, eax
0x180007842  xor     r9d, r9d; msWindowLength
0x180007845  xor     r8d, r8d; msPeriod
0x180007848  xor     edx, edx; pftDueTime
0x18000784a  mov     rcx, rsi; pti
0x18000784d  call    cs:__imp_SetThreadpoolTimer
0x180007853  mov     edx, 1; fCancelPendingCallbacks
0x180007858  mov     rcx, rsi; pti
0x18000785b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007861  mov     rcx, rsi; pti
0x180007864  call    cs:__imp_CloseThreadpoolTimer
0x18000786a  mov     ecx, ebx; dwErrCode
0x18000786c  call    cs:__imp_SetLastError
0x180007872  mov     qword ptr [rdi+30h], 0
0x18000787a  mov     rsi, [rdi+38h]
0x18000787e  test    rsi, rsi
0x180007881  jz      short loc_1800078BB
0x180007883  call    cs:__imp_GetLastError
0x180007889  mov     ebx, eax
0x18000788b  xor     r9d, r9d; msWindowLength
0x18000788e  xor     r8d, r8d; msPeriod
0x180007891  xor     edx, edx; pftDueTime
0x180007893  mov     rcx, rsi; pti
0x180007896  call    cs:__imp_SetThreadpoolTimer
0x18000789c  mov     edx, 1; fCancelPendingCallbacks
0x1800078a1  mov     rcx, rsi; pti
0x1800078a4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800078aa  mov     rcx, rsi; pti
0x1800078ad  call    cs:__imp_CloseThreadpoolTimer
0x1800078b3  mov     ecx, ebx; dwErrCode
0x1800078b5  call    cs:__imp_SetLastError
0x1800078bb  mov     qword ptr [rdi+38h], 0
0x1800078c3  mov     rbx, [rdi+100h]
0x1800078ca  mov     qword ptr [rdi+100h], 0
0x1800078d5  test    rbx, rbx
0x1800078d8  jz      short loc_1800078EE
0x1800078da  call    cs:__imp_GetProcessHeap
0x1800078e0  mov     rcx, rax; hHeap
0x1800078e3  mov     r8, rbx; lpMem
0x1800078e6  xor     edx, edx; dwFlags
0x1800078e8  call    cs:__imp_HeapFree
0x1800078ee  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800078f5  test    r8, r8
0x1800078f8  jz      short loc_180007912
0x1800078fa  mov     rdx, cs:qword_180016098; SRWLock
0x180007901  test    rdx, rdx
0x180007904  jz      short loc_180007912
0x180007906  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000790d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180007912  lea     rbx, [rdi+98h]
0x180007919  mov     rsi, [rbx+40h]
0x18000791d  mov     qword ptr [rbx+40h], 0
0x180007925  test    rsi, rsi
0x180007928  jz      short loc_18000793E
0x18000792a  call    cs:__imp_GetProcessHeap
0x180007930  mov     rcx, rax; hHeap
0x180007933  mov     r8, rsi; lpMem
0x180007936  xor     edx, edx; dwFlags
0x180007938  call    cs:__imp_HeapFree
0x18000793e  mov     rcx, rbx; lpCriticalSection
0x180007941  call    cs:__imp_DeleteCriticalSection
0x180007947  lea     rcx, [rdi+90h]
0x18000794e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180007953  mov     rsi, [rdi+88h]
0x18000795a  mov     qword ptr [rdi+88h], 0
0x180007965  test    rsi, rsi
0x180007968  jz      short loc_18000797E
0x18000796a  call    cs:__imp_GetProcessHeap
0x180007970  mov     rcx, rax; hHeap
0x180007973  mov     r8, rsi; lpMem
0x180007976  xor     edx, edx; dwFlags
0x180007978  call    cs:__imp_HeapFree
0x18000797e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180007982  call    cs:__imp_DeleteCriticalSection
0x180007988  mov     rbx, [rdi+38h]
0x18000798c  test    rbx, rbx
0x18000798f  jz      short loc_1800079B9
0x180007991  xor     r9d, r9d; msWindowLength
0x180007994  xor     r8d, r8d; msPeriod
0x180007997  xor     edx, edx; pftDueTime
0x180007999  mov     rcx, rbx; pti
0x18000799c  call    cs:__imp_SetThreadpoolTimer
0x1800079a2  mov     edx, 1; fCancelPendingCallbacks
0x1800079a7  mov     rcx, rbx; pti
0x1800079aa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800079b0  mov     rcx, rbx; pti
0x1800079b3  call    cs:__imp_CloseThreadpoolTimer
0x1800079b9  mov     rbx, [rdi+30h]
0x1800079bd  test    rbx, rbx
0x1800079c0  jz      short loc_1800079EB
0x1800079c2  xor     r9d, r9d; msWindowLength
0x1800079c5  xor     r8d, r8d; msPeriod
0x1800079c8  xor     edx, edx; pftDueTime
0x1800079ca  mov     rcx, rbx; pti
0x1800079cd  call    cs:__imp_SetThreadpoolTimer
0x1800079d3  mov     edx, 1; fCancelPendingCallbacks
0x1800079d8  mov     rcx, rbx; pti
0x1800079db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800079e1  mov     rcx, rbx; pti
0x1800079e4  call    cs:__imp_CloseThreadpoolTimer
0x1800079ea  nop
0x1800079eb  mov     rcx, [rdi+10h]; lpMem
0x1800079ef  test    rcx, rcx
0x1800079f2  jz      short loc_1800079FA
0x1800079f4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800079f9  nop
0x1800079fa  mov     rbx, [rsp+28h+arg_0]
0x1800079ff  mov     rsi, [rsp+28h+arg_8]
0x180007a04  add     rsp, 20h
0x180007a08  pop     rdi
0x180007a09  retn
```
