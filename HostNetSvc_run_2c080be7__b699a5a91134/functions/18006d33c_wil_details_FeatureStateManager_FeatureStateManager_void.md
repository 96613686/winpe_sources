# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18006d33c`
- end: `0x18006d52a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1802a8670`

## callees

- `0x18006ca6c`
- `0x18006d33c`
- `0x1800745a4`
- `0x180075e64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006d461`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006d4a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006d461`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006d4a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d3fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d44a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d48a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d3fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d44a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006d48a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d498`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006d498`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d38c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d3d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d38c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d3d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d3a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d384`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d3cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d4d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d504`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d384`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d3cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d4d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006d504`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d37b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d3c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d4ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d4fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d37b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d3c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d4ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006d4fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d36d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d3b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d4bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d4ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d36d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d3b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d4bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006d4ed`

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
  if ( v8 && qword_1803847B0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1803847B0[25], qword_1803847B0, v8);
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
0x18006d33c  mov     [rsp+arg_0], rbx
0x18006d341  mov     [rsp+arg_8], rsi
0x18006d346  push    rdi
0x18006d347  sub     rsp, 20h
0x18006d34b  mov     rdi, rcx
0x18006d34e  mov     byte ptr [rcx], 0
0x18006d351  mov     rsi, [rcx+30h]
0x18006d355  test    rsi, rsi
0x18006d358  jz      short loc_18006D392
0x18006d35a  call    cs:__imp_GetLastError
0x18006d360  mov     ebx, eax
0x18006d362  xor     r9d, r9d; msWindowLength
0x18006d365  xor     r8d, r8d; msPeriod
0x18006d368  xor     edx, edx; pftDueTime
0x18006d36a  mov     rcx, rsi; pti
0x18006d36d  call    cs:__imp_SetThreadpoolTimer
0x18006d373  mov     edx, 1; fCancelPendingCallbacks
0x18006d378  mov     rcx, rsi; pti
0x18006d37b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006d381  mov     rcx, rsi; pti
0x18006d384  call    cs:__imp_CloseThreadpoolTimer
0x18006d38a  mov     ecx, ebx; dwErrCode
0x18006d38c  call    cs:__imp_SetLastError
0x18006d392  mov     qword ptr [rdi+30h], 0
0x18006d39a  mov     rsi, [rdi+38h]
0x18006d39e  test    rsi, rsi
0x18006d3a1  jz      short loc_18006D3DB
0x18006d3a3  call    cs:__imp_GetLastError
0x18006d3a9  mov     ebx, eax
0x18006d3ab  xor     r9d, r9d; msWindowLength
0x18006d3ae  xor     r8d, r8d; msPeriod
0x18006d3b1  xor     edx, edx; pftDueTime
0x18006d3b3  mov     rcx, rsi; pti
0x18006d3b6  call    cs:__imp_SetThreadpoolTimer
0x18006d3bc  mov     edx, 1; fCancelPendingCallbacks
0x18006d3c1  mov     rcx, rsi; pti
0x18006d3c4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006d3ca  mov     rcx, rsi; pti
0x18006d3cd  call    cs:__imp_CloseThreadpoolTimer
0x18006d3d3  mov     ecx, ebx; dwErrCode
0x18006d3d5  call    cs:__imp_SetLastError
0x18006d3db  mov     qword ptr [rdi+38h], 0
0x18006d3e3  mov     rbx, [rdi+100h]
0x18006d3ea  mov     qword ptr [rdi+100h], 0
0x18006d3f5  test    rbx, rbx
0x18006d3f8  jz      short loc_18006D40E
0x18006d3fa  call    cs:__imp_GetProcessHeap
0x18006d400  mov     rcx, rax; hHeap
0x18006d403  mov     r8, rbx; lpMem
0x18006d406  xor     edx, edx; dwFlags
0x18006d408  call    cs:__imp_HeapFree
0x18006d40e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18006d415  test    r8, r8
0x18006d418  jz      short loc_18006D432
0x18006d41a  mov     rdx, cs:qword_1803847B0; SRWLock
0x18006d421  test    rdx, rdx
0x18006d424  jz      short loc_18006D432
0x18006d426  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18006d42d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18006d432  lea     rbx, [rdi+98h]
0x18006d439  mov     rsi, [rbx+40h]
0x18006d43d  mov     qword ptr [rbx+40h], 0
0x18006d445  test    rsi, rsi
0x18006d448  jz      short loc_18006D45E
0x18006d44a  call    cs:__imp_GetProcessHeap
0x18006d450  mov     rcx, rax; hHeap
0x18006d453  mov     r8, rsi; lpMem
0x18006d456  xor     edx, edx; dwFlags
0x18006d458  call    cs:__imp_HeapFree
0x18006d45e  mov     rcx, rbx; lpCriticalSection
0x18006d461  call    cs:__imp_DeleteCriticalSection
0x18006d467  lea     rcx, [rdi+90h]
0x18006d46e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d473  mov     rsi, [rdi+88h]
0x18006d47a  mov     qword ptr [rdi+88h], 0
0x18006d485  test    rsi, rsi
0x18006d488  jz      short loc_18006D49E
0x18006d48a  call    cs:__imp_GetProcessHeap
0x18006d490  mov     rcx, rax; hHeap
0x18006d493  mov     r8, rsi; lpMem
0x18006d496  xor     edx, edx; dwFlags
0x18006d498  call    cs:__imp_HeapFree
0x18006d49e  lea     rcx, [rdi+48h]; lpCriticalSection
0x18006d4a2  call    cs:__imp_DeleteCriticalSection
0x18006d4a8  mov     rbx, [rdi+38h]
0x18006d4ac  test    rbx, rbx
0x18006d4af  jz      short loc_18006D4D9
0x18006d4b1  xor     r9d, r9d; msWindowLength
0x18006d4b4  xor     r8d, r8d; msPeriod
0x18006d4b7  xor     edx, edx; pftDueTime
0x18006d4b9  mov     rcx, rbx; pti
0x18006d4bc  call    cs:__imp_SetThreadpoolTimer
0x18006d4c2  mov     edx, 1; fCancelPendingCallbacks
0x18006d4c7  mov     rcx, rbx; pti
0x18006d4ca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006d4d0  mov     rcx, rbx; pti
0x18006d4d3  call    cs:__imp_CloseThreadpoolTimer
0x18006d4d9  mov     rbx, [rdi+30h]
0x18006d4dd  test    rbx, rbx
0x18006d4e0  jz      short loc_18006D50B
0x18006d4e2  xor     r9d, r9d; msWindowLength
0x18006d4e5  xor     r8d, r8d; msPeriod
0x18006d4e8  xor     edx, edx; pftDueTime
0x18006d4ea  mov     rcx, rbx; pti
0x18006d4ed  call    cs:__imp_SetThreadpoolTimer
0x18006d4f3  mov     edx, 1; fCancelPendingCallbacks
0x18006d4f8  mov     rcx, rbx; pti
0x18006d4fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006d501  mov     rcx, rbx; pti
0x18006d504  call    cs:__imp_CloseThreadpoolTimer
0x18006d50a  nop
0x18006d50b  mov     rcx, [rdi+10h]; lpMem
0x18006d50f  test    rcx, rcx
0x18006d512  jz      short loc_18006D51A
0x18006d514  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18006d519  nop
0x18006d51a  mov     rbx, [rsp+28h+arg_0]
0x18006d51f  mov     rsi, [rsp+28h+arg_8]
0x18006d524  add     rsp, 20h
0x18006d528  pop     rdi
0x18006d529  retn
```
