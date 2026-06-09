# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180004808`
- end: `0x1800049f6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002ab10`

## callees

- `0x18000452c`
- `0x180004808`
- `0x1800088c0`
- `0x180009e58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000492d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000496e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000492d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000496e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004956`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004858`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000486f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000486f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004850`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004899`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000499f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004850`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004899`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000499f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004839`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004882`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004988`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004839`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004882`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004988`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004847`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004890`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004996`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004847`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004890`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004996`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_1800520D8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800520D8[25], qword_1800520D8, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x180004808  mov     [rsp+arg_0], rbx
0x18000480d  mov     [rsp+arg_8], rsi
0x180004812  push    rdi
0x180004813  sub     rsp, 20h
0x180004817  mov     rdi, rcx
0x18000481a  mov     byte ptr [rcx], 0
0x18000481d  mov     rsi, [rcx+30h]
0x180004821  test    rsi, rsi
0x180004824  jz      short loc_18000485E
0x180004826  call    cs:__imp_GetLastError
0x18000482c  mov     ebx, eax
0x18000482e  xor     r9d, r9d; msWindowLength
0x180004831  xor     r8d, r8d; msPeriod
0x180004834  xor     edx, edx; pftDueTime
0x180004836  mov     rcx, rsi; pti
0x180004839  call    cs:__imp_SetThreadpoolTimer
0x18000483f  mov     edx, 1; fCancelPendingCallbacks
0x180004844  mov     rcx, rsi; pti
0x180004847  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000484d  mov     rcx, rsi; pti
0x180004850  call    cs:__imp_CloseThreadpoolTimer
0x180004856  mov     ecx, ebx; dwErrCode
0x180004858  call    cs:__imp_SetLastError
0x18000485e  mov     qword ptr [rdi+30h], 0
0x180004866  mov     rsi, [rdi+38h]
0x18000486a  test    rsi, rsi
0x18000486d  jz      short loc_1800048A7
0x18000486f  call    cs:__imp_GetLastError
0x180004875  mov     ebx, eax
0x180004877  xor     r9d, r9d; msWindowLength
0x18000487a  xor     r8d, r8d; msPeriod
0x18000487d  xor     edx, edx; pftDueTime
0x18000487f  mov     rcx, rsi; pti
0x180004882  call    cs:__imp_SetThreadpoolTimer
0x180004888  mov     edx, 1; fCancelPendingCallbacks
0x18000488d  mov     rcx, rsi; pti
0x180004890  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004896  mov     rcx, rsi; pti
0x180004899  call    cs:__imp_CloseThreadpoolTimer
0x18000489f  mov     ecx, ebx; dwErrCode
0x1800048a1  call    cs:__imp_SetLastError
0x1800048a7  mov     qword ptr [rdi+38h], 0
0x1800048af  mov     rbx, [rdi+100h]
0x1800048b6  mov     qword ptr [rdi+100h], 0
0x1800048c1  test    rbx, rbx
0x1800048c4  jz      short loc_1800048DA
0x1800048c6  call    cs:__imp_GetProcessHeap
0x1800048cc  mov     rcx, rax; hHeap
0x1800048cf  mov     r8, rbx; lpMem
0x1800048d2  xor     edx, edx; dwFlags
0x1800048d4  call    cs:__imp_HeapFree
0x1800048da  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800048e1  test    r8, r8
0x1800048e4  jz      short loc_1800048FE
0x1800048e6  mov     rdx, cs:qword_1800520D8; SRWLock
0x1800048ed  test    rdx, rdx
0x1800048f0  jz      short loc_1800048FE
0x1800048f2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800048f9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800048fe  lea     rbx, [rdi+98h]
0x180004905  mov     rsi, [rbx+40h]
0x180004909  mov     qword ptr [rbx+40h], 0
0x180004911  test    rsi, rsi
0x180004914  jz      short loc_18000492A
0x180004916  call    cs:__imp_GetProcessHeap
0x18000491c  mov     rcx, rax; hHeap
0x18000491f  mov     r8, rsi; lpMem
0x180004922  xor     edx, edx; dwFlags
0x180004924  call    cs:__imp_HeapFree
0x18000492a  mov     rcx, rbx; lpCriticalSection
0x18000492d  call    cs:__imp_DeleteCriticalSection
0x180004933  lea     rcx, [rdi+90h]
0x18000493a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000493f  mov     rsi, [rdi+88h]
0x180004946  mov     qword ptr [rdi+88h], 0
0x180004951  test    rsi, rsi
0x180004954  jz      short loc_18000496A
0x180004956  call    cs:__imp_GetProcessHeap
0x18000495c  mov     rcx, rax; hHeap
0x18000495f  mov     r8, rsi; lpMem
0x180004962  xor     edx, edx; dwFlags
0x180004964  call    cs:__imp_HeapFree
0x18000496a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000496e  call    cs:__imp_DeleteCriticalSection
0x180004974  mov     rbx, [rdi+38h]
0x180004978  test    rbx, rbx
0x18000497b  jz      short loc_1800049A5
0x18000497d  xor     r9d, r9d; msWindowLength
0x180004980  xor     r8d, r8d; msPeriod
0x180004983  xor     edx, edx; pftDueTime
0x180004985  mov     rcx, rbx; pti
0x180004988  call    cs:__imp_SetThreadpoolTimer
0x18000498e  mov     edx, 1; fCancelPendingCallbacks
0x180004993  mov     rcx, rbx; pti
0x180004996  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000499c  mov     rcx, rbx; pti
0x18000499f  call    cs:__imp_CloseThreadpoolTimer
0x1800049a5  mov     rbx, [rdi+30h]
0x1800049a9  test    rbx, rbx
0x1800049ac  jz      short loc_1800049D7
0x1800049ae  xor     r9d, r9d; msWindowLength
0x1800049b1  xor     r8d, r8d; msPeriod
0x1800049b4  xor     edx, edx; pftDueTime
0x1800049b6  mov     rcx, rbx; pti
0x1800049b9  call    cs:__imp_SetThreadpoolTimer
0x1800049bf  mov     edx, 1; fCancelPendingCallbacks
0x1800049c4  mov     rcx, rbx; pti
0x1800049c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800049cd  mov     rcx, rbx; pti
0x1800049d0  call    cs:__imp_CloseThreadpoolTimer
0x1800049d6  nop
0x1800049d7  mov     rcx, [rdi+10h]; lpMem
0x1800049db  test    rcx, rcx
0x1800049de  jz      short loc_1800049E6
0x1800049e0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800049e5  nop
0x1800049e6  mov     rbx, [rsp+28h+arg_0]
0x1800049eb  mov     rsi, [rsp+28h+arg_8]
0x1800049f0  add     rsp, 20h
0x1800049f4  pop     rdi
0x1800049f5  retn
```
