# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000a238`
- end: `0x18000a3fc`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006f760`

## callees

- `0x18000a238`
- `0x18000d004`
- `0x18000e0b0`
- `0x18000e124`
- `0x18000e9ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a32a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a32a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a28b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a33e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a28b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a33e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a34e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a34e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a393`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a3d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a393`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a3d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a373`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a373`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a384`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a384`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v4 && qword_1800953B8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800953B8[25], qword_1800953B8, v4);
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
0x18000a238  push    rbx
0x18000a23a  push    rsi
0x18000a23b  push    rdi
0x18000a23c  push    r14
0x18000a23e  push    r15
0x18000a240  sub     rsp, 20h
0x18000a244  mov     rbx, rcx
0x18000a247  mov     byte ptr [rcx], 0
0x18000a24a  xor     edx, edx
0x18000a24c  add     rcx, 30h ; '0'
0x18000a250  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a255  xor     edx, edx
0x18000a257  lea     rcx, [rbx+38h]
0x18000a25b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a260  mov     rdi, [rbx+100h]
0x18000a267  mov     qword ptr [rbx+100h], 0
0x18000a272  test    rdi, rdi
0x18000a275  jz      short loc_18000A297
0x18000a277  call    cs:__imp_GetProcessHeap
0x18000a27e  nop     dword ptr [rax+rax+00h]
0x18000a283  mov     rcx, rax; hHeap
0x18000a286  mov     r8, rdi; lpMem
0x18000a289  xor     edx, edx; dwFlags
0x18000a28b  call    cs:__imp_HeapFree
0x18000a292  nop     dword ptr [rax+rax+00h]
0x18000a297  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000a29e  test    r8, r8
0x18000a2a1  jz      short loc_18000A2BB
0x18000a2a3  mov     rdx, cs:qword_1800953B8; SRWLock
0x18000a2aa  test    rdx, rdx
0x18000a2ad  jz      short loc_18000A2BB
0x18000a2af  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a2b6  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000a2bb  lea     rdi, [rbx+98h]
0x18000a2c2  mov     rsi, [rdi+40h]
0x18000a2c6  mov     qword ptr [rdi+40h], 0
0x18000a2ce  test    rsi, rsi
0x18000a2d1  jz      short loc_18000A2F3
0x18000a2d3  call    cs:__imp_GetProcessHeap
0x18000a2da  nop     dword ptr [rax+rax+00h]
0x18000a2df  mov     rcx, rax; hHeap
0x18000a2e2  mov     r8, rsi; lpMem
0x18000a2e5  xor     edx, edx; dwFlags
0x18000a2e7  call    cs:__imp_HeapFree
0x18000a2ee  nop     dword ptr [rax+rax+00h]
0x18000a2f3  mov     rcx, rdi; lpCriticalSection
0x18000a2f6  call    cs:__imp_DeleteCriticalSection
0x18000a2fd  nop     dword ptr [rax+rax+00h]
0x18000a302  mov     rcx, [rbx+90h]; this
0x18000a309  test    rcx, rcx
0x18000a30c  jz      short loc_18000A313
0x18000a30e  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000a313  mov     rsi, [rbx+88h]
0x18000a31a  mov     qword ptr [rbx+88h], 0
0x18000a325  test    rsi, rsi
0x18000a328  jz      short loc_18000A34A
0x18000a32a  call    cs:__imp_GetProcessHeap
0x18000a331  nop     dword ptr [rax+rax+00h]
0x18000a336  mov     rcx, rax; hHeap
0x18000a339  mov     r8, rsi; lpMem
0x18000a33c  xor     edx, edx; dwFlags
0x18000a33e  call    cs:__imp_HeapFree
0x18000a345  nop     dword ptr [rax+rax+00h]
0x18000a34a  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000a34e  call    cs:__imp_DeleteCriticalSection
0x18000a355  nop     dword ptr [rax+rax+00h]
0x18000a35a  mov     rdi, [rbx+38h]
0x18000a35e  mov     esi, 1
0x18000a363  test    rdi, rdi
0x18000a366  jz      short loc_18000A39F
0x18000a368  xor     r9d, r9d; msWindowLength
0x18000a36b  xor     r8d, r8d; msPeriod
0x18000a36e  xor     edx, edx; pftDueTime
0x18000a370  mov     rcx, rdi; pti
0x18000a373  call    cs:__imp_SetThreadpoolTimer
0x18000a37a  nop     dword ptr [rax+rax+00h]
0x18000a37f  mov     edx, esi; fCancelPendingCallbacks
0x18000a381  mov     rcx, rdi; pti
0x18000a384  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a38b  nop     dword ptr [rax+rax+00h]
0x18000a390  mov     rcx, rdi; pti
0x18000a393  call    cs:__imp_CloseThreadpoolTimer
0x18000a39a  nop     dword ptr [rax+rax+00h]
0x18000a39f  mov     rdi, [rbx+30h]
0x18000a3a3  test    rdi, rdi
0x18000a3a6  jz      short loc_18000A3E0
0x18000a3a8  xor     r9d, r9d; msWindowLength
0x18000a3ab  xor     r8d, r8d; msPeriod
0x18000a3ae  xor     edx, edx; pftDueTime
0x18000a3b0  mov     rcx, rdi; pti
0x18000a3b3  call    cs:__imp_SetThreadpoolTimer
0x18000a3ba  nop     dword ptr [rax+rax+00h]
0x18000a3bf  mov     edx, esi; fCancelPendingCallbacks
0x18000a3c1  mov     rcx, rdi; pti
0x18000a3c4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a3cb  nop     dword ptr [rax+rax+00h]
0x18000a3d0  mov     rcx, rdi; pti
0x18000a3d3  call    cs:__imp_CloseThreadpoolTimer
0x18000a3da  nop     dword ptr [rax+rax+00h]
0x18000a3df  nop
0x18000a3e0  mov     rcx, [rbx+10h]; lpMem
0x18000a3e4  test    rcx, rcx
0x18000a3e7  jz      short loc_18000A3EF
0x18000a3e9  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000a3ee  nop
0x18000a3ef  add     rsp, 20h
0x18000a3f3  pop     r15
0x18000a3f5  pop     r14
0x18000a3f7  pop     rdi
0x18000a3f8  pop     rsi
0x18000a3f9  pop     rbx
0x18000a3fa  retn
```
