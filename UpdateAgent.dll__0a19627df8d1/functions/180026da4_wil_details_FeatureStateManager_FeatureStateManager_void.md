# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180026da4`
- end: `0x180026f71`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `461`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1802abab0`

## callees

- `0x180026da4`
- `0x180083e50`
- `0x180096404`
- `0x180096478`
- `0x18009f330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026ec3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026ec3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026e9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026e00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026e5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026eb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026e00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026e5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026eb3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026ef9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026f39`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026ef9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026f39`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026f08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026f48`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026f08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026f48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026ee8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026f28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026ee8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026f28`

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
  if ( v4 && qword_1803A6550 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1803A6550[25], qword_1803A6550, v4);
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
0x180026da4  push    rbx
0x180026da6  push    rsi
0x180026da7  push    rdi
0x180026da8  push    r14
0x180026daa  push    r15
0x180026dac  sub     rsp, 30h
0x180026db0  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180026db9  mov     rbx, rcx
0x180026dbc  mov     byte ptr [rcx], 0
0x180026dbf  xor     edx, edx
0x180026dc1  add     rcx, 30h ; '0'
0x180026dc5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180026dca  xor     edx, edx
0x180026dcc  lea     rcx, [rbx+38h]
0x180026dd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180026dd5  mov     rdi, [rbx+100h]
0x180026ddc  mov     qword ptr [rbx+100h], 0
0x180026de7  test    rdi, rdi
0x180026dea  jz      short loc_180026E0C
0x180026dec  call    cs:__imp_GetProcessHeap
0x180026df3  nop     dword ptr [rax+rax+00h]
0x180026df8  mov     rcx, rax; hHeap
0x180026dfb  mov     r8, rdi; lpMem
0x180026dfe  xor     edx, edx; dwFlags
0x180026e00  call    cs:__imp_HeapFree
0x180026e07  nop     dword ptr [rax+rax+00h]
0x180026e0c  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180026e13  test    r8, r8
0x180026e16  jz      short loc_180026E30
0x180026e18  mov     rdx, cs:qword_1803A6550; SRWLock
0x180026e1f  test    rdx, rdx
0x180026e22  jz      short loc_180026E30
0x180026e24  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180026e2b  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180026e30  lea     rdi, [rbx+98h]
0x180026e37  mov     rsi, [rdi+40h]
0x180026e3b  mov     qword ptr [rdi+40h], 0
0x180026e43  test    rsi, rsi
0x180026e46  jz      short loc_180026E68
0x180026e48  call    cs:__imp_GetProcessHeap
0x180026e4f  nop     dword ptr [rax+rax+00h]
0x180026e54  mov     rcx, rax; hHeap
0x180026e57  mov     r8, rsi; lpMem
0x180026e5a  xor     edx, edx; dwFlags
0x180026e5c  call    cs:__imp_HeapFree
0x180026e63  nop     dword ptr [rax+rax+00h]
0x180026e68  mov     rcx, rdi; lpCriticalSection
0x180026e6b  call    cs:__imp_DeleteCriticalSection
0x180026e72  nop     dword ptr [rax+rax+00h]
0x180026e77  mov     rcx, [rbx+90h]; this
0x180026e7e  test    rcx, rcx
0x180026e81  jz      short loc_180026E88
0x180026e83  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180026e88  mov     rsi, [rbx+88h]
0x180026e8f  mov     qword ptr [rbx+88h], 0
0x180026e9a  test    rsi, rsi
0x180026e9d  jz      short loc_180026EBF
0x180026e9f  call    cs:__imp_GetProcessHeap
0x180026ea6  nop     dword ptr [rax+rax+00h]
0x180026eab  mov     rcx, rax; hHeap
0x180026eae  mov     r8, rsi; lpMem
0x180026eb1  xor     edx, edx; dwFlags
0x180026eb3  call    cs:__imp_HeapFree
0x180026eba  nop     dword ptr [rax+rax+00h]
0x180026ebf  lea     rcx, [rbx+48h]; lpCriticalSection
0x180026ec3  call    cs:__imp_DeleteCriticalSection
0x180026eca  nop     dword ptr [rax+rax+00h]
0x180026ecf  mov     rdi, [rbx+38h]
0x180026ed3  mov     esi, 1
0x180026ed8  test    rdi, rdi
0x180026edb  jz      short loc_180026F14
0x180026edd  xor     r9d, r9d; msWindowLength
0x180026ee0  xor     r8d, r8d; msPeriod
0x180026ee3  xor     edx, edx; pftDueTime
0x180026ee5  mov     rcx, rdi; pti
0x180026ee8  call    cs:__imp_SetThreadpoolTimer
0x180026eef  nop     dword ptr [rax+rax+00h]
0x180026ef4  mov     edx, esi; fCancelPendingCallbacks
0x180026ef6  mov     rcx, rdi; pti
0x180026ef9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180026f00  nop     dword ptr [rax+rax+00h]
0x180026f05  mov     rcx, rdi; pti
0x180026f08  call    cs:__imp_CloseThreadpoolTimer
0x180026f0f  nop     dword ptr [rax+rax+00h]
0x180026f14  mov     rdi, [rbx+30h]
0x180026f18  test    rdi, rdi
0x180026f1b  jz      short loc_180026F55
0x180026f1d  xor     r9d, r9d; msWindowLength
0x180026f20  xor     r8d, r8d; msPeriod
0x180026f23  xor     edx, edx; pftDueTime
0x180026f25  mov     rcx, rdi; pti
0x180026f28  call    cs:__imp_SetThreadpoolTimer
0x180026f2f  nop     dword ptr [rax+rax+00h]
0x180026f34  mov     edx, esi; fCancelPendingCallbacks
0x180026f36  mov     rcx, rdi; pti
0x180026f39  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180026f40  nop     dword ptr [rax+rax+00h]
0x180026f45  mov     rcx, rdi; pti
0x180026f48  call    cs:__imp_CloseThreadpoolTimer
0x180026f4f  nop     dword ptr [rax+rax+00h]
0x180026f54  nop
0x180026f55  mov     rcx, [rbx+10h]; lpMem
0x180026f59  test    rcx, rcx
0x180026f5c  jz      short loc_180026F64
0x180026f5e  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180026f63  nop
0x180026f64  add     rsp, 30h
0x180026f68  pop     r15
0x180026f6a  pop     r14
0x180026f6c  pop     rdi
0x180026f6d  pop     rsi
0x180026f6e  pop     rbx
0x180026f6f  retn
```
