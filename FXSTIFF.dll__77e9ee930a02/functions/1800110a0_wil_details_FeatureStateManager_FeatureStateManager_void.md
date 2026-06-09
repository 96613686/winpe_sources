# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800110a0`
- end: `0x180011264`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018eb0`

## callees

- `0x1800110a0`
- `0x180014d30`
- `0x18001608c`
- `0x180016100`
- `0x18001695c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800110f3`
- `KERNEL32!HeapFree` at `0x18001114f`
- `KERNEL32!HeapFree` at `0x1800111a6`
- `KERNEL32!HeapFree` at `0x1800110f3`
- `KERNEL32!HeapFree` at `0x18001114f`
- `KERNEL32!HeapFree` at `0x1800111a6`
- `KERNEL32!GetProcessHeap` at `0x1800110df`
- `KERNEL32!GetProcessHeap` at `0x18001113b`
- `KERNEL32!GetProcessHeap` at `0x180011192`
- `KERNEL32!GetProcessHeap` at `0x1800110df`
- `KERNEL32!GetProcessHeap` at `0x18001113b`
- `KERNEL32!GetProcessHeap` at `0x180011192`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800111ec`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001122c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800111ec`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001122c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800111fb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001123b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800111fb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001123b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800111db`
- `KERNEL32!SetThreadpoolTimer` at `0x18001121b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800111db`
- `KERNEL32!SetThreadpoolTimer` at `0x18001121b`
- `KERNEL32!DeleteCriticalSection` at `0x18001115e`
- `KERNEL32!DeleteCriticalSection` at `0x1800111b6`
- `KERNEL32!DeleteCriticalSection` at `0x18001115e`
- `KERNEL32!DeleteCriticalSection` at `0x1800111b6`

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
  if ( v4 && qword_180071020 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180071020[25], qword_180071020, v4);
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
0x1800110a0  push    rbx
0x1800110a2  push    rsi
0x1800110a3  push    rdi
0x1800110a4  push    r14
0x1800110a6  push    r15
0x1800110a8  sub     rsp, 20h
0x1800110ac  mov     rbx, rcx
0x1800110af  mov     byte ptr [rcx], 0
0x1800110b2  xor     edx, edx
0x1800110b4  add     rcx, 30h ; '0'
0x1800110b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800110bd  xor     edx, edx
0x1800110bf  lea     rcx, [rbx+38h]
0x1800110c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800110c8  mov     rdi, [rbx+100h]
0x1800110cf  mov     qword ptr [rbx+100h], 0
0x1800110da  test    rdi, rdi
0x1800110dd  jz      short loc_1800110FF
0x1800110df  call    cs:__imp_GetProcessHeap
0x1800110e6  nop     dword ptr [rax+rax+00h]
0x1800110eb  mov     rcx, rax; hHeap
0x1800110ee  mov     r8, rdi; lpMem
0x1800110f1  xor     edx, edx; dwFlags
0x1800110f3  call    cs:__imp_HeapFree
0x1800110fa  nop     dword ptr [rax+rax+00h]
0x1800110ff  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180011106  test    r8, r8
0x180011109  jz      short loc_180011123
0x18001110b  mov     rdx, cs:qword_180071020; SRWLock
0x180011112  test    rdx, rdx
0x180011115  jz      short loc_180011123
0x180011117  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001111e  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180011123  lea     rdi, [rbx+98h]
0x18001112a  mov     rsi, [rdi+40h]
0x18001112e  mov     qword ptr [rdi+40h], 0
0x180011136  test    rsi, rsi
0x180011139  jz      short loc_18001115B
0x18001113b  call    cs:__imp_GetProcessHeap
0x180011142  nop     dword ptr [rax+rax+00h]
0x180011147  mov     rcx, rax; hHeap
0x18001114a  mov     r8, rsi; lpMem
0x18001114d  xor     edx, edx; dwFlags
0x18001114f  call    cs:__imp_HeapFree
0x180011156  nop     dword ptr [rax+rax+00h]
0x18001115b  mov     rcx, rdi; lpCriticalSection
0x18001115e  call    cs:__imp_DeleteCriticalSection
0x180011165  nop     dword ptr [rax+rax+00h]
0x18001116a  mov     rcx, [rbx+90h]; this
0x180011171  test    rcx, rcx
0x180011174  jz      short loc_18001117B
0x180011176  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18001117b  mov     rsi, [rbx+88h]
0x180011182  mov     qword ptr [rbx+88h], 0
0x18001118d  test    rsi, rsi
0x180011190  jz      short loc_1800111B2
0x180011192  call    cs:__imp_GetProcessHeap
0x180011199  nop     dword ptr [rax+rax+00h]
0x18001119e  mov     rcx, rax; hHeap
0x1800111a1  mov     r8, rsi; lpMem
0x1800111a4  xor     edx, edx; dwFlags
0x1800111a6  call    cs:__imp_HeapFree
0x1800111ad  nop     dword ptr [rax+rax+00h]
0x1800111b2  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800111b6  call    cs:__imp_DeleteCriticalSection
0x1800111bd  nop     dword ptr [rax+rax+00h]
0x1800111c2  mov     rdi, [rbx+38h]
0x1800111c6  mov     esi, 1
0x1800111cb  test    rdi, rdi
0x1800111ce  jz      short loc_180011207
0x1800111d0  xor     r9d, r9d; msWindowLength
0x1800111d3  xor     r8d, r8d; msPeriod
0x1800111d6  xor     edx, edx; pftDueTime
0x1800111d8  mov     rcx, rdi; pti
0x1800111db  call    cs:__imp_SetThreadpoolTimer
0x1800111e2  nop     dword ptr [rax+rax+00h]
0x1800111e7  mov     edx, esi; fCancelPendingCallbacks
0x1800111e9  mov     rcx, rdi; pti
0x1800111ec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800111f3  nop     dword ptr [rax+rax+00h]
0x1800111f8  mov     rcx, rdi; pti
0x1800111fb  call    cs:__imp_CloseThreadpoolTimer
0x180011202  nop     dword ptr [rax+rax+00h]
0x180011207  mov     rdi, [rbx+30h]
0x18001120b  test    rdi, rdi
0x18001120e  jz      short loc_180011248
0x180011210  xor     r9d, r9d; msWindowLength
0x180011213  xor     r8d, r8d; msPeriod
0x180011216  xor     edx, edx; pftDueTime
0x180011218  mov     rcx, rdi; pti
0x18001121b  call    cs:__imp_SetThreadpoolTimer
0x180011222  nop     dword ptr [rax+rax+00h]
0x180011227  mov     edx, esi; fCancelPendingCallbacks
0x180011229  mov     rcx, rdi; pti
0x18001122c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011233  nop     dword ptr [rax+rax+00h]
0x180011238  mov     rcx, rdi; pti
0x18001123b  call    cs:__imp_CloseThreadpoolTimer
0x180011242  nop     dword ptr [rax+rax+00h]
0x180011247  nop
0x180011248  mov     rcx, [rbx+10h]; lpMem
0x18001124c  test    rcx, rcx
0x18001124f  jz      short loc_180011257
0x180011251  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180011256  nop
0x180011257  add     rsp, 20h
0x18001125b  pop     r15
0x18001125d  pop     r14
0x18001125f  pop     rdi
0x180011260  pop     rsi
0x180011261  pop     rbx
0x180011262  retn
```
