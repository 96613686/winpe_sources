# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001548c`
- end: `0x180015650`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180037060`

## callees

- `0x18001548c`
- `0x18001a880`
- `0x18001fa5c`
- `0x18001fad0`
- `0x180021b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001554a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800155a2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001554a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800155a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800154cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015527`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001557e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800154cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015527`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001557e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800154df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001553b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800154df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001553b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015592`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800155d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015618`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800155d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015618`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800155e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015627`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800155e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015627`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800155c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015607`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800155c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015607`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v4; // r8
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rsi
  HANDLE v10; // rax
  struct _TP_TIMER *v11; // rdi
  struct _TP_TIMER *v12; // rdi
  void *v13; // rcx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 48,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 56,
    0);
  v2 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v4 && qword_18004B200 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18004B200[25], qword_18004B200, v4);
  v5 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v8 = (wil::details *)*((_QWORD *)this + 18);
  if ( v8 )
    wil::details::UnregisterWilFeatureConfigurationChange(v8, v7);
  v9 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v11 )
  {
    SetThreadpoolTimer(v11, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v11, 1);
    CloseThreadpoolTimer(v11);
  }
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v12 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
  v13 = (void *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x18001548c  push    rbx
0x18001548e  push    rsi
0x18001548f  push    rdi
0x180015490  push    r14
0x180015492  push    r15
0x180015494  sub     rsp, 20h
0x180015498  mov     rbx, rcx
0x18001549b  mov     byte ptr [rcx], 0
0x18001549e  xor     edx, edx
0x1800154a0  add     rcx, 30h ; '0'
0x1800154a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800154a9  xor     edx, edx
0x1800154ab  lea     rcx, [rbx+38h]
0x1800154af  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800154b4  mov     rdi, [rbx+100h]
0x1800154bb  mov     qword ptr [rbx+100h], 0
0x1800154c6  test    rdi, rdi
0x1800154c9  jz      short loc_1800154EB
0x1800154cb  call    cs:__imp_GetProcessHeap
0x1800154d2  nop     dword ptr [rax+rax+00h]
0x1800154d7  mov     rcx, rax; hHeap
0x1800154da  mov     r8, rdi; lpMem
0x1800154dd  xor     edx, edx; dwFlags
0x1800154df  call    cs:__imp_HeapFree
0x1800154e6  nop     dword ptr [rax+rax+00h]
0x1800154eb  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800154f2  test    r8, r8
0x1800154f5  jz      short loc_18001550F
0x1800154f7  mov     rdx, cs:qword_18004B200; SRWLock
0x1800154fe  test    rdx, rdx
0x180015501  jz      short loc_18001550F
0x180015503  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001550a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001550f  lea     rdi, [rbx+98h]
0x180015516  mov     rsi, [rdi+40h]
0x18001551a  mov     qword ptr [rdi+40h], 0
0x180015522  test    rsi, rsi
0x180015525  jz      short loc_180015547
0x180015527  call    cs:__imp_GetProcessHeap
0x18001552e  nop     dword ptr [rax+rax+00h]
0x180015533  mov     rcx, rax; hHeap
0x180015536  mov     r8, rsi; lpMem
0x180015539  xor     edx, edx; dwFlags
0x18001553b  call    cs:__imp_HeapFree
0x180015542  nop     dword ptr [rax+rax+00h]
0x180015547  mov     rcx, rdi; lpCriticalSection
0x18001554a  call    cs:__imp_DeleteCriticalSection
0x180015551  nop     dword ptr [rax+rax+00h]
0x180015556  mov     rcx, [rbx+90h]; this
0x18001555d  test    rcx, rcx
0x180015560  jz      short loc_180015567
0x180015562  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180015567  mov     rsi, [rbx+88h]
0x18001556e  mov     qword ptr [rbx+88h], 0
0x180015579  test    rsi, rsi
0x18001557c  jz      short loc_18001559E
0x18001557e  call    cs:__imp_GetProcessHeap
0x180015585  nop     dword ptr [rax+rax+00h]
0x18001558a  mov     rcx, rax; hHeap
0x18001558d  mov     r8, rsi; lpMem
0x180015590  xor     edx, edx; dwFlags
0x180015592  call    cs:__imp_HeapFree
0x180015599  nop     dword ptr [rax+rax+00h]
0x18001559e  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800155a2  call    cs:__imp_DeleteCriticalSection
0x1800155a9  nop     dword ptr [rax+rax+00h]
0x1800155ae  mov     rdi, [rbx+38h]
0x1800155b2  mov     esi, 1
0x1800155b7  test    rdi, rdi
0x1800155ba  jz      short loc_1800155F3
0x1800155bc  xor     r9d, r9d; msWindowLength
0x1800155bf  xor     r8d, r8d; msPeriod
0x1800155c2  xor     edx, edx; pftDueTime
0x1800155c4  mov     rcx, rdi; pti
0x1800155c7  call    cs:__imp_SetThreadpoolTimer
0x1800155ce  nop     dword ptr [rax+rax+00h]
0x1800155d3  mov     edx, esi; fCancelPendingCallbacks
0x1800155d5  mov     rcx, rdi; pti
0x1800155d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800155df  nop     dword ptr [rax+rax+00h]
0x1800155e4  mov     rcx, rdi; pti
0x1800155e7  call    cs:__imp_CloseThreadpoolTimer
0x1800155ee  nop     dword ptr [rax+rax+00h]
0x1800155f3  mov     rdi, [rbx+30h]
0x1800155f7  test    rdi, rdi
0x1800155fa  jz      short loc_180015634
0x1800155fc  xor     r9d, r9d; msWindowLength
0x1800155ff  xor     r8d, r8d; msPeriod
0x180015602  xor     edx, edx; pftDueTime
0x180015604  mov     rcx, rdi; pti
0x180015607  call    cs:__imp_SetThreadpoolTimer
0x18001560e  nop     dword ptr [rax+rax+00h]
0x180015613  mov     edx, esi; fCancelPendingCallbacks
0x180015615  mov     rcx, rdi; pti
0x180015618  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001561f  nop     dword ptr [rax+rax+00h]
0x180015624  mov     rcx, rdi; pti
0x180015627  call    cs:__imp_CloseThreadpoolTimer
0x18001562e  nop     dword ptr [rax+rax+00h]
0x180015633  nop
0x180015634  mov     rcx, [rbx+10h]; lpMem
0x180015638  test    rcx, rcx
0x18001563b  jz      short loc_180015643
0x18001563d  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180015642  nop
0x180015643  add     rsp, 20h
0x180015647  pop     r15
0x180015649  pop     r14
0x18001564b  pop     rdi
0x18001564c  pop     rsi
0x18001564d  pop     rbx
0x18001564e  retn
```
