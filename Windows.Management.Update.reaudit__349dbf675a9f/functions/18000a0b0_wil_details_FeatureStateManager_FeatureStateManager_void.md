# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000a0b0`
- end: `0x18000a287`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `471`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002b110`

## callees

- `0x18000a0b0`
- `0x18000e5e8`
- `0x18000fe44`
- `0x18000feb8`
- `0x180010774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a175`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a175`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a22f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a1ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a22f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a200`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a240`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a200`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a240`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a20f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a24f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a20f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a24f`

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
  if ( v4 && qword_18003C080 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18003C080[25], qword_18003C080, v4);
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
0x18000a0b0  mov     rax, rsp
0x18000a0b3  mov     [rax+8], rbx
0x18000a0b7  mov     [rax+10h], rsi
0x18000a0bb  mov     [rax+18h], rdi
0x18000a0bf  mov     [rax+20h], r14
0x18000a0c3  push    r15
0x18000a0c5  sub     rsp, 20h
0x18000a0c9  mov     rbx, rcx
0x18000a0cc  mov     byte ptr [rcx], 0
0x18000a0cf  xor     edx, edx
0x18000a0d1  add     rcx, 30h ; '0'
0x18000a0d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a0da  xor     edx, edx
0x18000a0dc  lea     rcx, [rbx+38h]
0x18000a0e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a0e5  mov     rdi, [rbx+100h]
0x18000a0ec  and     qword ptr [rbx+100h], 0
0x18000a0f4  test    rdi, rdi
0x18000a0f7  jz      short loc_18000A119
0x18000a0f9  call    cs:__imp_GetProcessHeap
0x18000a100  nop     dword ptr [rax+rax+00h]
0x18000a105  mov     rcx, rax; hHeap
0x18000a108  mov     r8, rdi; lpMem
0x18000a10b  xor     edx, edx; dwFlags
0x18000a10d  call    cs:__imp_HeapFree
0x18000a114  nop     dword ptr [rax+rax+00h]
0x18000a119  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000a120  test    r8, r8
0x18000a123  jz      short loc_18000A13D
0x18000a125  mov     rdx, cs:qword_18003C080; SRWLock
0x18000a12c  test    rdx, rdx
0x18000a12f  jz      short loc_18000A13D
0x18000a131  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000a138  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000a13d  lea     rdi, [rbx+98h]
0x18000a144  mov     rsi, [rdi+40h]
0x18000a148  and     qword ptr [rdi+40h], 0
0x18000a14d  test    rsi, rsi
0x18000a150  jz      short loc_18000A172
0x18000a152  call    cs:__imp_GetProcessHeap
0x18000a159  nop     dword ptr [rax+rax+00h]
0x18000a15e  mov     rcx, rax; hHeap
0x18000a161  mov     r8, rsi; lpMem
0x18000a164  xor     edx, edx; dwFlags
0x18000a166  call    cs:__imp_HeapFree
0x18000a16d  nop     dword ptr [rax+rax+00h]
0x18000a172  mov     rcx, rdi; lpCriticalSection
0x18000a175  call    cs:__imp_DeleteCriticalSection
0x18000a17c  nop     dword ptr [rax+rax+00h]
0x18000a181  mov     rcx, [rbx+90h]; this
0x18000a188  test    rcx, rcx
0x18000a18b  jz      short loc_18000A192
0x18000a18d  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000a192  mov     rsi, [rbx+88h]
0x18000a199  and     qword ptr [rbx+88h], 0
0x18000a1a1  test    rsi, rsi
0x18000a1a4  jz      short loc_18000A1C6
0x18000a1a6  call    cs:__imp_GetProcessHeap
0x18000a1ad  nop     dword ptr [rax+rax+00h]
0x18000a1b2  mov     rcx, rax; hHeap
0x18000a1b5  mov     r8, rsi; lpMem
0x18000a1b8  xor     edx, edx; dwFlags
0x18000a1ba  call    cs:__imp_HeapFree
0x18000a1c1  nop     dword ptr [rax+rax+00h]
0x18000a1c6  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000a1ca  call    cs:__imp_DeleteCriticalSection
0x18000a1d1  nop     dword ptr [rax+rax+00h]
0x18000a1d6  mov     rdi, [rbx+38h]
0x18000a1da  mov     esi, 1
0x18000a1df  test    rdi, rdi
0x18000a1e2  jz      short loc_18000A21B
0x18000a1e4  xor     r9d, r9d; msWindowLength
0x18000a1e7  xor     r8d, r8d; msPeriod
0x18000a1ea  xor     edx, edx; pftDueTime
0x18000a1ec  mov     rcx, rdi; pti
0x18000a1ef  call    cs:__imp_SetThreadpoolTimer
0x18000a1f6  nop     dword ptr [rax+rax+00h]
0x18000a1fb  mov     edx, esi; fCancelPendingCallbacks
0x18000a1fd  mov     rcx, rdi; pti
0x18000a200  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a207  nop     dword ptr [rax+rax+00h]
0x18000a20c  mov     rcx, rdi; pti
0x18000a20f  call    cs:__imp_CloseThreadpoolTimer
0x18000a216  nop     dword ptr [rax+rax+00h]
0x18000a21b  mov     rdi, [rbx+30h]
0x18000a21f  test    rdi, rdi
0x18000a222  jz      short loc_18000A25C
0x18000a224  xor     r9d, r9d; msWindowLength
0x18000a227  xor     r8d, r8d; msPeriod
0x18000a22a  xor     edx, edx; pftDueTime
0x18000a22c  mov     rcx, rdi; pti
0x18000a22f  call    cs:__imp_SetThreadpoolTimer
0x18000a236  nop     dword ptr [rax+rax+00h]
0x18000a23b  mov     edx, esi; fCancelPendingCallbacks
0x18000a23d  mov     rcx, rdi; pti
0x18000a240  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a247  nop     dword ptr [rax+rax+00h]
0x18000a24c  mov     rcx, rdi; pti
0x18000a24f  call    cs:__imp_CloseThreadpoolTimer
0x18000a256  nop     dword ptr [rax+rax+00h]
0x18000a25b  nop
0x18000a25c  mov     rcx, [rbx+10h]; lpMem
0x18000a260  test    rcx, rcx
0x18000a263  jz      short loc_18000A26B
0x18000a265  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000a26a  nop
0x18000a26b  mov     rbx, [rsp+28h+arg_0]
0x18000a270  mov     rsi, [rsp+28h+arg_8]
0x18000a275  mov     rdi, [rsp+28h+arg_10]
0x18000a27a  mov     r14, [rsp+28h+arg_18]
0x18000a27f  add     rsp, 20h
0x18000a283  pop     r15
0x18000a285  retn
```
