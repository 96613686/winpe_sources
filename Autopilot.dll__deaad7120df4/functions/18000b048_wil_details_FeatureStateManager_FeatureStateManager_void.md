# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000b048`
- end: `0x18000b20c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002e190`

## callees

- `0x18000b048`
- `0x180010000`
- `0x180011abc`
- `0x180011b30`
- `0x1800125b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b106`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b15e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b106`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b15e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b087`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b13a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b087`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b13a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b09b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b14e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b09b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b14e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b194`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b194`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b183`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b183`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1c3`

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
  if ( v4 && qword_180043170 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180043170[25], qword_180043170, v4);
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
0x18000b048  push    rbx
0x18000b04a  push    rsi
0x18000b04b  push    rdi
0x18000b04c  push    r14
0x18000b04e  push    r15
0x18000b050  sub     rsp, 20h
0x18000b054  mov     rbx, rcx
0x18000b057  mov     byte ptr [rcx], 0
0x18000b05a  xor     edx, edx
0x18000b05c  add     rcx, 30h ; '0'
0x18000b060  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b065  xor     edx, edx
0x18000b067  lea     rcx, [rbx+38h]
0x18000b06b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b070  mov     rdi, [rbx+100h]
0x18000b077  mov     qword ptr [rbx+100h], 0
0x18000b082  test    rdi, rdi
0x18000b085  jz      short loc_18000B0A7
0x18000b087  call    cs:__imp_GetProcessHeap
0x18000b08e  nop     dword ptr [rax+rax+00h]
0x18000b093  mov     rcx, rax; hHeap
0x18000b096  mov     r8, rdi; lpMem
0x18000b099  xor     edx, edx; dwFlags
0x18000b09b  call    cs:__imp_HeapFree
0x18000b0a2  nop     dword ptr [rax+rax+00h]
0x18000b0a7  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000b0ae  test    r8, r8
0x18000b0b1  jz      short loc_18000B0CB
0x18000b0b3  mov     rdx, cs:qword_180043170; SRWLock
0x18000b0ba  test    rdx, rdx
0x18000b0bd  jz      short loc_18000B0CB
0x18000b0bf  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b0c6  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000b0cb  lea     rdi, [rbx+98h]
0x18000b0d2  mov     rsi, [rdi+40h]
0x18000b0d6  mov     qword ptr [rdi+40h], 0
0x18000b0de  test    rsi, rsi
0x18000b0e1  jz      short loc_18000B103
0x18000b0e3  call    cs:__imp_GetProcessHeap
0x18000b0ea  nop     dword ptr [rax+rax+00h]
0x18000b0ef  mov     rcx, rax; hHeap
0x18000b0f2  mov     r8, rsi; lpMem
0x18000b0f5  xor     edx, edx; dwFlags
0x18000b0f7  call    cs:__imp_HeapFree
0x18000b0fe  nop     dword ptr [rax+rax+00h]
0x18000b103  mov     rcx, rdi; lpCriticalSection
0x18000b106  call    cs:__imp_DeleteCriticalSection
0x18000b10d  nop     dword ptr [rax+rax+00h]
0x18000b112  mov     rcx, [rbx+90h]; this
0x18000b119  test    rcx, rcx
0x18000b11c  jz      short loc_18000B123
0x18000b11e  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000b123  mov     rsi, [rbx+88h]
0x18000b12a  mov     qword ptr [rbx+88h], 0
0x18000b135  test    rsi, rsi
0x18000b138  jz      short loc_18000B15A
0x18000b13a  call    cs:__imp_GetProcessHeap
0x18000b141  nop     dword ptr [rax+rax+00h]
0x18000b146  mov     rcx, rax; hHeap
0x18000b149  mov     r8, rsi; lpMem
0x18000b14c  xor     edx, edx; dwFlags
0x18000b14e  call    cs:__imp_HeapFree
0x18000b155  nop     dword ptr [rax+rax+00h]
0x18000b15a  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000b15e  call    cs:__imp_DeleteCriticalSection
0x18000b165  nop     dword ptr [rax+rax+00h]
0x18000b16a  mov     rdi, [rbx+38h]
0x18000b16e  mov     esi, 1
0x18000b173  test    rdi, rdi
0x18000b176  jz      short loc_18000B1AF
0x18000b178  xor     r9d, r9d; msWindowLength
0x18000b17b  xor     r8d, r8d; msPeriod
0x18000b17e  xor     edx, edx; pftDueTime
0x18000b180  mov     rcx, rdi; pti
0x18000b183  call    cs:__imp_SetThreadpoolTimer
0x18000b18a  nop     dword ptr [rax+rax+00h]
0x18000b18f  mov     edx, esi; fCancelPendingCallbacks
0x18000b191  mov     rcx, rdi; pti
0x18000b194  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b19b  nop     dword ptr [rax+rax+00h]
0x18000b1a0  mov     rcx, rdi; pti
0x18000b1a3  call    cs:__imp_CloseThreadpoolTimer
0x18000b1aa  nop     dword ptr [rax+rax+00h]
0x18000b1af  mov     rdi, [rbx+30h]
0x18000b1b3  test    rdi, rdi
0x18000b1b6  jz      short loc_18000B1F0
0x18000b1b8  xor     r9d, r9d; msWindowLength
0x18000b1bb  xor     r8d, r8d; msPeriod
0x18000b1be  xor     edx, edx; pftDueTime
0x18000b1c0  mov     rcx, rdi; pti
0x18000b1c3  call    cs:__imp_SetThreadpoolTimer
0x18000b1ca  nop     dword ptr [rax+rax+00h]
0x18000b1cf  mov     edx, esi; fCancelPendingCallbacks
0x18000b1d1  mov     rcx, rdi; pti
0x18000b1d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b1db  nop     dword ptr [rax+rax+00h]
0x18000b1e0  mov     rcx, rdi; pti
0x18000b1e3  call    cs:__imp_CloseThreadpoolTimer
0x18000b1ea  nop     dword ptr [rax+rax+00h]
0x18000b1ef  nop
0x18000b1f0  mov     rcx, [rbx+10h]; lpMem
0x18000b1f4  test    rcx, rcx
0x18000b1f7  jz      short loc_18000B1FF
0x18000b1f9  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000b1fe  nop
0x18000b1ff  add     rsp, 20h
0x18000b203  pop     r15
0x18000b205  pop     r14
0x18000b207  pop     rdi
0x18000b208  pop     rsi
0x18000b209  pop     rbx
0x18000b20a  retn
```
