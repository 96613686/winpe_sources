# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140004484`
- end: `0x14000466c`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `488`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140081a40`

## callees

- `0x140004484`
- `0x14001ce04`
- `0x140020294`
- `0x140020308`
- `0x140021310`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1400045d4`
- `KERNEL32!SetThreadpoolTimer` at `0x140004614`
- `KERNEL32!SetThreadpoolTimer` at `0x1400045d4`
- `KERNEL32!SetThreadpoolTimer` at `0x140004614`
- `KERNEL32!DeleteCriticalSection` at `0x140004557`
- `KERNEL32!DeleteCriticalSection` at `0x1400045af`
- `KERNEL32!DeleteCriticalSection` at `0x140004557`
- `KERNEL32!DeleteCriticalSection` at `0x1400045af`
- `KERNEL32!HeapFree` at `0x1400044ec`
- `KERNEL32!HeapFree` at `0x140004548`
- `KERNEL32!HeapFree` at `0x14000459f`
- `KERNEL32!HeapFree` at `0x1400044ec`
- `KERNEL32!HeapFree` at `0x140004548`
- `KERNEL32!HeapFree` at `0x14000459f`
- `KERNEL32!GetProcessHeap` at `0x1400044d8`
- `KERNEL32!GetProcessHeap` at `0x140004534`
- `KERNEL32!GetProcessHeap` at `0x14000458b`
- `KERNEL32!GetProcessHeap` at `0x1400044d8`
- `KERNEL32!GetProcessHeap` at `0x140004534`
- `KERNEL32!GetProcessHeap` at `0x14000458b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400045f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004634`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400045f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004634`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400045e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004625`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400045e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004625`

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
  if ( v4 && qword_1400A5078 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400A5078[25], qword_1400A5078, v4);
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
0x140004484  mov     rax, rsp
0x140004487  push    r15
0x140004489  sub     rsp, 30h
0x14000448d  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x140004495  mov     [rax+8], rbx
0x140004499  mov     [rax+10h], rsi
0x14000449d  mov     [rax+18h], rdi
0x1400044a1  mov     [rax+20h], r14
0x1400044a5  mov     rbx, rcx
0x1400044a8  mov     byte ptr [rcx], 0
0x1400044ab  xor     edx, edx
0x1400044ad  add     rcx, 30h ; '0'
0x1400044b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400044b6  xor     edx, edx
0x1400044b8  lea     rcx, [rbx+38h]
0x1400044bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400044c1  mov     rdi, [rbx+100h]
0x1400044c8  mov     qword ptr [rbx+100h], 0
0x1400044d3  test    rdi, rdi
0x1400044d6  jz      short loc_1400044F8
0x1400044d8  call    cs:__imp_GetProcessHeap
0x1400044df  nop     dword ptr [rax+rax+00h]
0x1400044e4  mov     rcx, rax; hHeap
0x1400044e7  mov     r8, rdi; lpMem
0x1400044ea  xor     edx, edx; dwFlags
0x1400044ec  call    cs:__imp_HeapFree
0x1400044f3  nop     dword ptr [rax+rax+00h]
0x1400044f8  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400044ff  test    r8, r8
0x140004502  jz      short loc_14000451C
0x140004504  mov     rdx, cs:qword_1400A5078; SRWLock
0x14000450b  test    rdx, rdx
0x14000450e  jz      short loc_14000451C
0x140004510  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140004517  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000451c  lea     rdi, [rbx+98h]
0x140004523  mov     rsi, [rdi+40h]
0x140004527  mov     qword ptr [rdi+40h], 0
0x14000452f  test    rsi, rsi
0x140004532  jz      short loc_140004554
0x140004534  call    cs:__imp_GetProcessHeap
0x14000453b  nop     dword ptr [rax+rax+00h]
0x140004540  mov     rcx, rax; hHeap
0x140004543  mov     r8, rsi; lpMem
0x140004546  xor     edx, edx; dwFlags
0x140004548  call    cs:__imp_HeapFree
0x14000454f  nop     dword ptr [rax+rax+00h]
0x140004554  mov     rcx, rdi; lpCriticalSection
0x140004557  call    cs:__imp_DeleteCriticalSection
0x14000455e  nop     dword ptr [rax+rax+00h]
0x140004563  mov     rcx, [rbx+90h]; this
0x14000456a  test    rcx, rcx
0x14000456d  jz      short loc_140004574
0x14000456f  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x140004574  mov     rsi, [rbx+88h]
0x14000457b  mov     qword ptr [rbx+88h], 0
0x140004586  test    rsi, rsi
0x140004589  jz      short loc_1400045AB
0x14000458b  call    cs:__imp_GetProcessHeap
0x140004592  nop     dword ptr [rax+rax+00h]
0x140004597  mov     rcx, rax; hHeap
0x14000459a  mov     r8, rsi; lpMem
0x14000459d  xor     edx, edx; dwFlags
0x14000459f  call    cs:__imp_HeapFree
0x1400045a6  nop     dword ptr [rax+rax+00h]
0x1400045ab  lea     rcx, [rbx+48h]; lpCriticalSection
0x1400045af  call    cs:__imp_DeleteCriticalSection
0x1400045b6  nop     dword ptr [rax+rax+00h]
0x1400045bb  mov     rdi, [rbx+38h]
0x1400045bf  mov     esi, 1
0x1400045c4  test    rdi, rdi
0x1400045c7  jz      short loc_140004600
0x1400045c9  xor     r9d, r9d; msWindowLength
0x1400045cc  xor     r8d, r8d; msPeriod
0x1400045cf  xor     edx, edx; pftDueTime
0x1400045d1  mov     rcx, rdi; pti
0x1400045d4  call    cs:__imp_SetThreadpoolTimer
0x1400045db  nop     dword ptr [rax+rax+00h]
0x1400045e0  mov     edx, esi; fCancelPendingCallbacks
0x1400045e2  mov     rcx, rdi; pti
0x1400045e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400045ec  nop     dword ptr [rax+rax+00h]
0x1400045f1  mov     rcx, rdi; pti
0x1400045f4  call    cs:__imp_CloseThreadpoolTimer
0x1400045fb  nop     dword ptr [rax+rax+00h]
0x140004600  mov     rdi, [rbx+30h]
0x140004604  test    rdi, rdi
0x140004607  jz      short loc_140004641
0x140004609  xor     r9d, r9d; msWindowLength
0x14000460c  xor     r8d, r8d; msPeriod
0x14000460f  xor     edx, edx; pftDueTime
0x140004611  mov     rcx, rdi; pti
0x140004614  call    cs:__imp_SetThreadpoolTimer
0x14000461b  nop     dword ptr [rax+rax+00h]
0x140004620  mov     edx, esi; fCancelPendingCallbacks
0x140004622  mov     rcx, rdi; pti
0x140004625  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000462c  nop     dword ptr [rax+rax+00h]
0x140004631  mov     rcx, rdi; pti
0x140004634  call    cs:__imp_CloseThreadpoolTimer
0x14000463b  nop     dword ptr [rax+rax+00h]
0x140004640  nop
0x140004641  mov     rcx, [rbx+10h]; lpMem
0x140004645  test    rcx, rcx
0x140004648  jz      short loc_140004650
0x14000464a  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000464f  nop
0x140004650  mov     rbx, [rsp+38h+arg_0]
0x140004655  mov     rsi, [rsp+38h+arg_8]
0x14000465a  mov     rdi, [rsp+38h+arg_10]
0x14000465f  mov     r14, [rsp+38h+arg_18]
0x140004664  add     rsp, 30h
0x140004668  pop     r15
0x14000466a  retn
```
