# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000f248`
- end: `0x18000f436`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b070`

## callees

- `0x18000efa4`
- `0x18000f248`
- `0x180011fdc`
- `0x180013dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f36d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f3ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f36d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f3ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f306`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f396`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f306`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f314`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f314`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f3a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f298`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f298`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f287`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f2d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f3d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f407`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f287`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f2d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f3d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f407`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f279`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f2c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f3c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f3f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f279`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f2c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f3c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f3f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f290`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f2d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f3df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f410`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f290`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f2d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f3df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f410`

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
  if ( v8 && qword_1800440F0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800440F0[25], qword_1800440F0, v8);
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
0x18000f248  mov     [rsp+arg_0], rbx
0x18000f24d  mov     [rsp+arg_8], rsi
0x18000f252  push    rdi
0x18000f253  sub     rsp, 20h
0x18000f257  mov     rdi, rcx
0x18000f25a  mov     byte ptr [rcx], 0
0x18000f25d  mov     rsi, [rcx+30h]
0x18000f261  test    rsi, rsi
0x18000f264  jz      short loc_18000F29E
0x18000f266  call    cs:__imp_GetLastError
0x18000f26c  mov     ebx, eax
0x18000f26e  xor     r9d, r9d; msWindowLength
0x18000f271  xor     r8d, r8d; msPeriod
0x18000f274  xor     edx, edx; pftDueTime
0x18000f276  mov     rcx, rsi; pti
0x18000f279  call    cs:__imp_SetThreadpoolTimer
0x18000f27f  mov     edx, 1; fCancelPendingCallbacks
0x18000f284  mov     rcx, rsi; pti
0x18000f287  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f28d  mov     rcx, rsi; pti
0x18000f290  call    cs:__imp_CloseThreadpoolTimer
0x18000f296  mov     ecx, ebx; dwErrCode
0x18000f298  call    cs:__imp_SetLastError
0x18000f29e  mov     qword ptr [rdi+30h], 0
0x18000f2a6  mov     rsi, [rdi+38h]
0x18000f2aa  test    rsi, rsi
0x18000f2ad  jz      short loc_18000F2E7
0x18000f2af  call    cs:__imp_GetLastError
0x18000f2b5  mov     ebx, eax
0x18000f2b7  xor     r9d, r9d; msWindowLength
0x18000f2ba  xor     r8d, r8d; msPeriod
0x18000f2bd  xor     edx, edx; pftDueTime
0x18000f2bf  mov     rcx, rsi; pti
0x18000f2c2  call    cs:__imp_SetThreadpoolTimer
0x18000f2c8  mov     edx, 1; fCancelPendingCallbacks
0x18000f2cd  mov     rcx, rsi; pti
0x18000f2d0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f2d6  mov     rcx, rsi; pti
0x18000f2d9  call    cs:__imp_CloseThreadpoolTimer
0x18000f2df  mov     ecx, ebx; dwErrCode
0x18000f2e1  call    cs:__imp_SetLastError
0x18000f2e7  mov     qword ptr [rdi+38h], 0
0x18000f2ef  mov     rbx, [rdi+100h]
0x18000f2f6  mov     qword ptr [rdi+100h], 0
0x18000f301  test    rbx, rbx
0x18000f304  jz      short loc_18000F31A
0x18000f306  call    cs:__imp_GetProcessHeap
0x18000f30c  mov     rcx, rax; hHeap
0x18000f30f  mov     r8, rbx; lpMem
0x18000f312  xor     edx, edx; dwFlags
0x18000f314  call    cs:__imp_HeapFree
0x18000f31a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000f321  test    r8, r8
0x18000f324  jz      short loc_18000F33E
0x18000f326  mov     rdx, cs:qword_1800440F0; SRWLock
0x18000f32d  test    rdx, rdx
0x18000f330  jz      short loc_18000F33E
0x18000f332  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000f339  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000f33e  lea     rbx, [rdi+98h]
0x18000f345  mov     rsi, [rbx+40h]
0x18000f349  mov     qword ptr [rbx+40h], 0
0x18000f351  test    rsi, rsi
0x18000f354  jz      short loc_18000F36A
0x18000f356  call    cs:__imp_GetProcessHeap
0x18000f35c  mov     rcx, rax; hHeap
0x18000f35f  mov     r8, rsi; lpMem
0x18000f362  xor     edx, edx; dwFlags
0x18000f364  call    cs:__imp_HeapFree
0x18000f36a  mov     rcx, rbx; lpCriticalSection
0x18000f36d  call    cs:__imp_DeleteCriticalSection
0x18000f373  lea     rcx, [rdi+90h]
0x18000f37a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000f37f  mov     rsi, [rdi+88h]
0x18000f386  mov     qword ptr [rdi+88h], 0
0x18000f391  test    rsi, rsi
0x18000f394  jz      short loc_18000F3AA
0x18000f396  call    cs:__imp_GetProcessHeap
0x18000f39c  mov     rcx, rax; hHeap
0x18000f39f  mov     r8, rsi; lpMem
0x18000f3a2  xor     edx, edx; dwFlags
0x18000f3a4  call    cs:__imp_HeapFree
0x18000f3aa  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000f3ae  call    cs:__imp_DeleteCriticalSection
0x18000f3b4  mov     rbx, [rdi+38h]
0x18000f3b8  test    rbx, rbx
0x18000f3bb  jz      short loc_18000F3E5
0x18000f3bd  xor     r9d, r9d; msWindowLength
0x18000f3c0  xor     r8d, r8d; msPeriod
0x18000f3c3  xor     edx, edx; pftDueTime
0x18000f3c5  mov     rcx, rbx; pti
0x18000f3c8  call    cs:__imp_SetThreadpoolTimer
0x18000f3ce  mov     edx, 1; fCancelPendingCallbacks
0x18000f3d3  mov     rcx, rbx; pti
0x18000f3d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f3dc  mov     rcx, rbx; pti
0x18000f3df  call    cs:__imp_CloseThreadpoolTimer
0x18000f3e5  mov     rbx, [rdi+30h]
0x18000f3e9  test    rbx, rbx
0x18000f3ec  jz      short loc_18000F417
0x18000f3ee  xor     r9d, r9d; msWindowLength
0x18000f3f1  xor     r8d, r8d; msPeriod
0x18000f3f4  xor     edx, edx; pftDueTime
0x18000f3f6  mov     rcx, rbx; pti
0x18000f3f9  call    cs:__imp_SetThreadpoolTimer
0x18000f3ff  mov     edx, 1; fCancelPendingCallbacks
0x18000f404  mov     rcx, rbx; pti
0x18000f407  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f40d  mov     rcx, rbx; pti
0x18000f410  call    cs:__imp_CloseThreadpoolTimer
0x18000f416  nop
0x18000f417  mov     rcx, [rdi+10h]; lpMem
0x18000f41b  test    rcx, rcx
0x18000f41e  jz      short loc_18000F426
0x18000f420  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000f425  nop
0x18000f426  mov     rbx, [rsp+28h+arg_0]
0x18000f42b  mov     rsi, [rsp+28h+arg_8]
0x18000f430  add     rsp, 20h
0x18000f434  pop     rdi
0x18000f435  retn
```
