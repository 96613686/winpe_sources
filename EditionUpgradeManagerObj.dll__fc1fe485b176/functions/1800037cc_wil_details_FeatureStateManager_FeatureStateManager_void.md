# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800037cc`
- end: `0x1800039b8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022b70`

## callees

- `0x18000353c`
- `0x1800037cc`
- `0x180007274`
- `0x1800080a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003932`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003932`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003898`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003928`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003898`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003928`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000391a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000388a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000391a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000381c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003865`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000381c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003833`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000380b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003854`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000395a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000398b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000380b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003854`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000395a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000398b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003814`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000385d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003963`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003994`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003814`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000385d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003963`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003994`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003846`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000394c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000397d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003846`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000394c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000397d`

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
  if ( v8 && qword_18002F258 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18002F258[25], qword_18002F258, v8);
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
0x1800037cc  mov     [rsp+arg_0], rbx
0x1800037d1  mov     [rsp+arg_8], rsi
0x1800037d6  push    rdi
0x1800037d7  sub     rsp, 20h
0x1800037db  mov     byte ptr [rcx], 0
0x1800037de  mov     rdi, rcx
0x1800037e1  mov     rsi, [rcx+30h]
0x1800037e5  test    rsi, rsi
0x1800037e8  jz      short loc_180003822
0x1800037ea  call    cs:__imp_GetLastError
0x1800037f0  xor     r9d, r9d; msWindowLength
0x1800037f3  xor     r8d, r8d; msPeriod
0x1800037f6  xor     edx, edx; pftDueTime
0x1800037f8  mov     rcx, rsi; pti
0x1800037fb  mov     ebx, eax
0x1800037fd  call    cs:__imp_SetThreadpoolTimer
0x180003803  mov     edx, 1; fCancelPendingCallbacks
0x180003808  mov     rcx, rsi; pti
0x18000380b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003811  mov     rcx, rsi; pti
0x180003814  call    cs:__imp_CloseThreadpoolTimer
0x18000381a  mov     ecx, ebx; dwErrCode
0x18000381c  call    cs:__imp_SetLastError
0x180003822  mov     qword ptr [rdi+30h], 0
0x18000382a  mov     rsi, [rdi+38h]
0x18000382e  test    rsi, rsi
0x180003831  jz      short loc_18000386B
0x180003833  call    cs:__imp_GetLastError
0x180003839  xor     r9d, r9d; msWindowLength
0x18000383c  xor     r8d, r8d; msPeriod
0x18000383f  xor     edx, edx; pftDueTime
0x180003841  mov     rcx, rsi; pti
0x180003844  mov     ebx, eax
0x180003846  call    cs:__imp_SetThreadpoolTimer
0x18000384c  mov     edx, 1; fCancelPendingCallbacks
0x180003851  mov     rcx, rsi; pti
0x180003854  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000385a  mov     rcx, rsi; pti
0x18000385d  call    cs:__imp_CloseThreadpoolTimer
0x180003863  mov     ecx, ebx; dwErrCode
0x180003865  call    cs:__imp_SetLastError
0x18000386b  mov     qword ptr [rdi+38h], 0
0x180003873  mov     rbx, [rdi+100h]
0x18000387a  mov     qword ptr [rdi+100h], 0
0x180003885  test    rbx, rbx
0x180003888  jz      short loc_18000389E
0x18000388a  call    cs:__imp_GetProcessHeap
0x180003890  mov     r8, rbx; lpMem
0x180003893  xor     edx, edx; dwFlags
0x180003895  mov     rcx, rax; hHeap
0x180003898  call    cs:__imp_HeapFree
0x18000389e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800038a5  test    r8, r8
0x1800038a8  jz      short loc_1800038C2
0x1800038aa  mov     rdx, cs:qword_18002F258; SRWLock
0x1800038b1  test    rdx, rdx
0x1800038b4  jz      short loc_1800038C2
0x1800038b6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800038bd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800038c2  lea     rbx, [rdi+98h]
0x1800038c9  mov     rsi, [rbx+40h]
0x1800038cd  mov     qword ptr [rbx+40h], 0
0x1800038d5  test    rsi, rsi
0x1800038d8  jz      short loc_1800038EE
0x1800038da  call    cs:__imp_GetProcessHeap
0x1800038e0  mov     r8, rsi; lpMem
0x1800038e3  xor     edx, edx; dwFlags
0x1800038e5  mov     rcx, rax; hHeap
0x1800038e8  call    cs:__imp_HeapFree
0x1800038ee  mov     rcx, rbx; lpCriticalSection
0x1800038f1  call    cs:__imp_DeleteCriticalSection
0x1800038f7  lea     rcx, [rdi+90h]
0x1800038fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003903  mov     rsi, [rdi+88h]
0x18000390a  mov     qword ptr [rdi+88h], 0
0x180003915  test    rsi, rsi
0x180003918  jz      short loc_18000392E
0x18000391a  call    cs:__imp_GetProcessHeap
0x180003920  mov     r8, rsi; lpMem
0x180003923  xor     edx, edx; dwFlags
0x180003925  mov     rcx, rax; hHeap
0x180003928  call    cs:__imp_HeapFree
0x18000392e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003932  call    cs:__imp_DeleteCriticalSection
0x180003938  mov     rbx, [rdi+38h]
0x18000393c  test    rbx, rbx
0x18000393f  jz      short loc_180003969
0x180003941  xor     r9d, r9d; msWindowLength
0x180003944  xor     r8d, r8d; msPeriod
0x180003947  xor     edx, edx; pftDueTime
0x180003949  mov     rcx, rbx; pti
0x18000394c  call    cs:__imp_SetThreadpoolTimer
0x180003952  mov     edx, 1; fCancelPendingCallbacks
0x180003957  mov     rcx, rbx; pti
0x18000395a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003960  mov     rcx, rbx; pti
0x180003963  call    cs:__imp_CloseThreadpoolTimer
0x180003969  mov     rbx, [rdi+30h]
0x18000396d  test    rbx, rbx
0x180003970  jz      short loc_18000399A
0x180003972  xor     r9d, r9d; msWindowLength
0x180003975  xor     r8d, r8d; msPeriod
0x180003978  xor     edx, edx; pftDueTime
0x18000397a  mov     rcx, rbx; pti
0x18000397d  call    cs:__imp_SetThreadpoolTimer
0x180003983  mov     edx, 1; fCancelPendingCallbacks
0x180003988  mov     rcx, rbx; pti
0x18000398b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003991  mov     rcx, rbx; pti
0x180003994  call    cs:__imp_CloseThreadpoolTimer
0x18000399a  mov     rcx, [rdi+10h]; lpMem
0x18000399e  test    rcx, rcx
0x1800039a1  jz      short loc_1800039A8
0x1800039a3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800039a8  mov     rbx, [rsp+28h+arg_0]
0x1800039ad  mov     rsi, [rsp+28h+arg_8]
0x1800039b2  add     rsp, 20h
0x1800039b6  pop     rdi
0x1800039b7  retn
```
