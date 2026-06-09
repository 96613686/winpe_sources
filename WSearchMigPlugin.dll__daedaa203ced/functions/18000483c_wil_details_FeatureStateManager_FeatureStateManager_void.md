# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000483c`
- end: `0x180004a34`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `504`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017c70`

## callees

- `0x1800045d8`
- `0x18000483c`
- `0x18000856c`
- `0x1800098c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000496b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000496b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004904`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004954`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004904`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004954`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004994`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004912`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004912`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800049a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004877`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049f7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004877`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000488e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800048d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004a0e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000488e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800048d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004a0e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004885`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800048ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004a05`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004885`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800048ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004a05`

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
  if ( v8 && qword_180025408 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180025408[25], qword_180025408, v8);
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
0x18000483c  push    rdi
0x18000483e  sub     rsp, 30h
0x180004842  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000484b  mov     [rsp+38h+arg_0], rbx
0x180004850  mov     [rsp+38h+arg_8], rsi
0x180004855  mov     rdi, rcx
0x180004858  mov     byte ptr [rcx], 0
0x18000485b  mov     rsi, [rcx+30h]
0x18000485f  test    rsi, rsi
0x180004862  jz      short loc_18000489C
0x180004864  call    cs:__imp_GetLastError
0x18000486a  mov     ebx, eax
0x18000486c  xor     r9d, r9d; msWindowLength
0x18000486f  xor     r8d, r8d; msPeriod
0x180004872  xor     edx, edx; pftDueTime
0x180004874  mov     rcx, rsi; pti
0x180004877  call    cs:__imp_SetThreadpoolTimer
0x18000487d  mov     edx, 1; fCancelPendingCallbacks
0x180004882  mov     rcx, rsi; pti
0x180004885  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000488b  mov     rcx, rsi; pti
0x18000488e  call    cs:__imp_CloseThreadpoolTimer
0x180004894  mov     ecx, ebx; dwErrCode
0x180004896  call    cs:__imp_SetLastError
0x18000489c  mov     qword ptr [rdi+30h], 0
0x1800048a4  mov     rsi, [rdi+38h]
0x1800048a8  test    rsi, rsi
0x1800048ab  jz      short loc_1800048E5
0x1800048ad  call    cs:__imp_GetLastError
0x1800048b3  mov     ebx, eax
0x1800048b5  xor     r9d, r9d; msWindowLength
0x1800048b8  xor     r8d, r8d; msPeriod
0x1800048bb  xor     edx, edx; pftDueTime
0x1800048bd  mov     rcx, rsi; pti
0x1800048c0  call    cs:__imp_SetThreadpoolTimer
0x1800048c6  mov     edx, 1; fCancelPendingCallbacks
0x1800048cb  mov     rcx, rsi; pti
0x1800048ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800048d4  mov     rcx, rsi; pti
0x1800048d7  call    cs:__imp_CloseThreadpoolTimer
0x1800048dd  mov     ecx, ebx; dwErrCode
0x1800048df  call    cs:__imp_SetLastError
0x1800048e5  mov     qword ptr [rdi+38h], 0
0x1800048ed  mov     rbx, [rdi+100h]
0x1800048f4  mov     qword ptr [rdi+100h], 0
0x1800048ff  test    rbx, rbx
0x180004902  jz      short loc_180004918
0x180004904  call    cs:__imp_GetProcessHeap
0x18000490a  mov     rcx, rax; hHeap
0x18000490d  mov     r8, rbx; lpMem
0x180004910  xor     edx, edx; dwFlags
0x180004912  call    cs:__imp_HeapFree
0x180004918  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000491f  test    r8, r8
0x180004922  jz      short loc_18000493C
0x180004924  mov     rdx, cs:qword_180025408; SRWLock
0x18000492b  test    rdx, rdx
0x18000492e  jz      short loc_18000493C
0x180004930  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180004937  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000493c  lea     rbx, [rdi+98h]
0x180004943  mov     rsi, [rbx+40h]
0x180004947  mov     qword ptr [rbx+40h], 0
0x18000494f  test    rsi, rsi
0x180004952  jz      short loc_180004968
0x180004954  call    cs:__imp_GetProcessHeap
0x18000495a  mov     rcx, rax; hHeap
0x18000495d  mov     r8, rsi; lpMem
0x180004960  xor     edx, edx; dwFlags
0x180004962  call    cs:__imp_HeapFree
0x180004968  mov     rcx, rbx; lpCriticalSection
0x18000496b  call    cs:__imp_DeleteCriticalSection
0x180004971  lea     rcx, [rdi+90h]
0x180004978  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000497d  mov     rsi, [rdi+88h]
0x180004984  mov     qword ptr [rdi+88h], 0
0x18000498f  test    rsi, rsi
0x180004992  jz      short loc_1800049A8
0x180004994  call    cs:__imp_GetProcessHeap
0x18000499a  mov     rcx, rax; hHeap
0x18000499d  mov     r8, rsi; lpMem
0x1800049a0  xor     edx, edx; dwFlags
0x1800049a2  call    cs:__imp_HeapFree
0x1800049a8  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800049ac  call    cs:__imp_DeleteCriticalSection
0x1800049b2  mov     rbx, [rdi+38h]
0x1800049b6  test    rbx, rbx
0x1800049b9  jz      short loc_1800049E3
0x1800049bb  xor     r9d, r9d; msWindowLength
0x1800049be  xor     r8d, r8d; msPeriod
0x1800049c1  xor     edx, edx; pftDueTime
0x1800049c3  mov     rcx, rbx; pti
0x1800049c6  call    cs:__imp_SetThreadpoolTimer
0x1800049cc  mov     edx, 1; fCancelPendingCallbacks
0x1800049d1  mov     rcx, rbx; pti
0x1800049d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800049da  mov     rcx, rbx; pti
0x1800049dd  call    cs:__imp_CloseThreadpoolTimer
0x1800049e3  mov     rbx, [rdi+30h]
0x1800049e7  test    rbx, rbx
0x1800049ea  jz      short loc_180004A15
0x1800049ec  xor     r9d, r9d; msWindowLength
0x1800049ef  xor     r8d, r8d; msPeriod
0x1800049f2  xor     edx, edx; pftDueTime
0x1800049f4  mov     rcx, rbx; pti
0x1800049f7  call    cs:__imp_SetThreadpoolTimer
0x1800049fd  mov     edx, 1; fCancelPendingCallbacks
0x180004a02  mov     rcx, rbx; pti
0x180004a05  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004a0b  mov     rcx, rbx; pti
0x180004a0e  call    cs:__imp_CloseThreadpoolTimer
0x180004a14  nop
0x180004a15  mov     rcx, [rdi+10h]; lpMem
0x180004a19  test    rcx, rcx
0x180004a1c  jz      short loc_180004A24
0x180004a1e  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004a23  nop
0x180004a24  mov     rbx, [rsp+38h+arg_0]
0x180004a29  mov     rsi, [rsp+38h+arg_8]
0x180004a2e  add     rsp, 30h
0x180004a32  pop     rdi
0x180004a33  retn
```
