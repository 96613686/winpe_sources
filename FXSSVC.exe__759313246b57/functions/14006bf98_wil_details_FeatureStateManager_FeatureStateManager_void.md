# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14006bf98`
- end: `0x14006c15c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14008a2d0`

## callees

- `0x14006bf98`
- `0x14006fbbc`
- `0x140070f68`
- `0x140070fdc`
- `0x1400717b8`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x14006c0d3`
- `KERNEL32!SetThreadpoolTimer` at `0x14006c113`
- `KERNEL32!SetThreadpoolTimer` at `0x14006c0d3`
- `KERNEL32!SetThreadpoolTimer` at `0x14006c113`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006c0f3`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006c133`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006c0f3`
- `KERNEL32!CloseThreadpoolTimer` at `0x14006c133`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006c0e4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006c124`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006c0e4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006c124`
- `KERNEL32!GetProcessHeap` at `0x14006bfd7`
- `KERNEL32!GetProcessHeap` at `0x14006c033`
- `KERNEL32!GetProcessHeap` at `0x14006c08a`
- `KERNEL32!GetProcessHeap` at `0x14006bfd7`
- `KERNEL32!GetProcessHeap` at `0x14006c033`
- `KERNEL32!GetProcessHeap` at `0x14006c08a`
- `KERNEL32!HeapFree` at `0x14006bfeb`
- `KERNEL32!HeapFree` at `0x14006c047`
- `KERNEL32!HeapFree` at `0x14006c09e`
- `KERNEL32!HeapFree` at `0x14006bfeb`
- `KERNEL32!HeapFree` at `0x14006c047`
- `KERNEL32!HeapFree` at `0x14006c09e`
- `KERNEL32!DeleteCriticalSection` at `0x14006c056`
- `KERNEL32!DeleteCriticalSection` at `0x14006c0ae`
- `KERNEL32!DeleteCriticalSection` at `0x14006c056`
- `KERNEL32!DeleteCriticalSection` at `0x14006c0ae`

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
  if ( v4 && SRWLock )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&SRWLock[25], SRWLock, v4);
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
0x14006bf98  push    rbx
0x14006bf9a  push    rsi
0x14006bf9b  push    rdi
0x14006bf9c  push    r14
0x14006bf9e  push    r15
0x14006bfa0  sub     rsp, 20h
0x14006bfa4  mov     rbx, rcx
0x14006bfa7  mov     byte ptr [rcx], 0
0x14006bfaa  xor     edx, edx
0x14006bfac  add     rcx, 30h ; '0'
0x14006bfb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14006bfb5  xor     edx, edx
0x14006bfb7  lea     rcx, [rbx+38h]
0x14006bfbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14006bfc0  mov     rdi, [rbx+100h]
0x14006bfc7  mov     qword ptr [rbx+100h], 0
0x14006bfd2  test    rdi, rdi
0x14006bfd5  jz      short loc_14006BFF7
0x14006bfd7  call    cs:__imp_GetProcessHeap
0x14006bfde  nop     dword ptr [rax+rax+00h]
0x14006bfe3  mov     rcx, rax; hHeap
0x14006bfe6  mov     r8, rdi; lpMem
0x14006bfe9  xor     edx, edx; dwFlags
0x14006bfeb  call    cs:__imp_HeapFree
0x14006bff2  nop     dword ptr [rax+rax+00h]
0x14006bff7  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14006bffe  test    r8, r8
0x14006c001  jz      short loc_14006C01B
0x14006c003  mov     rdx, cs:SRWLock; SRWLock
0x14006c00a  test    rdx, rdx
0x14006c00d  jz      short loc_14006C01B
0x14006c00f  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14006c016  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14006c01b  lea     rdi, [rbx+98h]
0x14006c022  mov     rsi, [rdi+40h]
0x14006c026  mov     qword ptr [rdi+40h], 0
0x14006c02e  test    rsi, rsi
0x14006c031  jz      short loc_14006C053
0x14006c033  call    cs:__imp_GetProcessHeap
0x14006c03a  nop     dword ptr [rax+rax+00h]
0x14006c03f  mov     rcx, rax; hHeap
0x14006c042  mov     r8, rsi; lpMem
0x14006c045  xor     edx, edx; dwFlags
0x14006c047  call    cs:__imp_HeapFree
0x14006c04e  nop     dword ptr [rax+rax+00h]
0x14006c053  mov     rcx, rdi; lpCriticalSection
0x14006c056  call    cs:__imp_DeleteCriticalSection
0x14006c05d  nop     dword ptr [rax+rax+00h]
0x14006c062  mov     rcx, [rbx+90h]; this
0x14006c069  test    rcx, rcx
0x14006c06c  jz      short loc_14006C073
0x14006c06e  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x14006c073  mov     rsi, [rbx+88h]
0x14006c07a  mov     qword ptr [rbx+88h], 0
0x14006c085  test    rsi, rsi
0x14006c088  jz      short loc_14006C0AA
0x14006c08a  call    cs:__imp_GetProcessHeap
0x14006c091  nop     dword ptr [rax+rax+00h]
0x14006c096  mov     rcx, rax; hHeap
0x14006c099  mov     r8, rsi; lpMem
0x14006c09c  xor     edx, edx; dwFlags
0x14006c09e  call    cs:__imp_HeapFree
0x14006c0a5  nop     dword ptr [rax+rax+00h]
0x14006c0aa  lea     rcx, [rbx+48h]; lpCriticalSection
0x14006c0ae  call    cs:__imp_DeleteCriticalSection
0x14006c0b5  nop     dword ptr [rax+rax+00h]
0x14006c0ba  mov     rdi, [rbx+38h]
0x14006c0be  mov     esi, 1
0x14006c0c3  test    rdi, rdi
0x14006c0c6  jz      short loc_14006C0FF
0x14006c0c8  xor     r9d, r9d; msWindowLength
0x14006c0cb  xor     r8d, r8d; msPeriod
0x14006c0ce  xor     edx, edx; pftDueTime
0x14006c0d0  mov     rcx, rdi; pti
0x14006c0d3  call    cs:__imp_SetThreadpoolTimer
0x14006c0da  nop     dword ptr [rax+rax+00h]
0x14006c0df  mov     edx, esi; fCancelPendingCallbacks
0x14006c0e1  mov     rcx, rdi; pti
0x14006c0e4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14006c0eb  nop     dword ptr [rax+rax+00h]
0x14006c0f0  mov     rcx, rdi; pti
0x14006c0f3  call    cs:__imp_CloseThreadpoolTimer
0x14006c0fa  nop     dword ptr [rax+rax+00h]
0x14006c0ff  mov     rdi, [rbx+30h]
0x14006c103  test    rdi, rdi
0x14006c106  jz      short loc_14006C140
0x14006c108  xor     r9d, r9d; msWindowLength
0x14006c10b  xor     r8d, r8d; msPeriod
0x14006c10e  xor     edx, edx; pftDueTime
0x14006c110  mov     rcx, rdi; pti
0x14006c113  call    cs:__imp_SetThreadpoolTimer
0x14006c11a  nop     dword ptr [rax+rax+00h]
0x14006c11f  mov     edx, esi; fCancelPendingCallbacks
0x14006c121  mov     rcx, rdi; pti
0x14006c124  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14006c12b  nop     dword ptr [rax+rax+00h]
0x14006c130  mov     rcx, rdi; pti
0x14006c133  call    cs:__imp_CloseThreadpoolTimer
0x14006c13a  nop     dword ptr [rax+rax+00h]
0x14006c13f  nop
0x14006c140  mov     rcx, [rbx+10h]; lpMem
0x14006c144  test    rcx, rcx
0x14006c147  jz      short loc_14006C14F
0x14006c149  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14006c14e  nop
0x14006c14f  add     rsp, 20h
0x14006c153  pop     r15
0x14006c155  pop     r14
0x14006c157  pop     rdi
0x14006c158  pop     rsi
0x14006c159  pop     rbx
0x14006c15a  retn
```
