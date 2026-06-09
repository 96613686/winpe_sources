# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000309c`
- end: `0x180003260`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `452`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003d9e0`

## callees

- `0x18000309c`
- `0x18000785c`
- `0x180008ebc`
- `0x180008f30`
- `0x18000981c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800030db`
- `KERNEL32!GetProcessHeap` at `0x180003137`
- `KERNEL32!GetProcessHeap` at `0x18000318e`
- `KERNEL32!GetProcessHeap` at `0x1800030db`
- `KERNEL32!GetProcessHeap` at `0x180003137`
- `KERNEL32!GetProcessHeap` at `0x18000318e`
- `KERNEL32!DeleteCriticalSection` at `0x18000315a`
- `KERNEL32!DeleteCriticalSection` at `0x1800031b2`
- `KERNEL32!DeleteCriticalSection` at `0x18000315a`
- `KERNEL32!DeleteCriticalSection` at `0x1800031b2`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800031f7`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003237`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800031f7`
- `KERNEL32!CloseThreadpoolTimer` at `0x180003237`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800031e8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003228`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800031e8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180003228`
- `KERNEL32!SetThreadpoolTimer` at `0x1800031d7`
- `KERNEL32!SetThreadpoolTimer` at `0x180003217`
- `KERNEL32!SetThreadpoolTimer` at `0x1800031d7`
- `KERNEL32!SetThreadpoolTimer` at `0x180003217`
- `KERNEL32!HeapFree` at `0x1800030ef`
- `KERNEL32!HeapFree` at `0x18000314b`
- `KERNEL32!HeapFree` at `0x1800031a2`
- `KERNEL32!HeapFree` at `0x1800030ef`
- `KERNEL32!HeapFree` at `0x18000314b`
- `KERNEL32!HeapFree` at `0x1800031a2`

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
  if ( v4 && qword_18004E040 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18004E040[25], qword_18004E040, v4);
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
0x18000309c  push    rbx
0x18000309e  push    rsi
0x18000309f  push    rdi
0x1800030a0  push    r14
0x1800030a2  push    r15
0x1800030a4  sub     rsp, 20h
0x1800030a8  mov     rbx, rcx
0x1800030ab  mov     byte ptr [rcx], 0
0x1800030ae  xor     edx, edx
0x1800030b0  add     rcx, 30h ; '0'
0x1800030b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800030b9  xor     edx, edx
0x1800030bb  lea     rcx, [rbx+38h]
0x1800030bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800030c4  mov     rdi, [rbx+100h]
0x1800030cb  mov     qword ptr [rbx+100h], 0
0x1800030d6  test    rdi, rdi
0x1800030d9  jz      short loc_1800030FB
0x1800030db  call    cs:__imp_GetProcessHeap
0x1800030e2  nop     dword ptr [rax+rax+00h]
0x1800030e7  mov     rcx, rax; hHeap
0x1800030ea  mov     r8, rdi; lpMem
0x1800030ed  xor     edx, edx; dwFlags
0x1800030ef  call    cs:__imp_HeapFree
0x1800030f6  nop     dword ptr [rax+rax+00h]
0x1800030fb  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003102  test    r8, r8
0x180003105  jz      short loc_18000311F
0x180003107  mov     rdx, cs:qword_18004E040; SRWLock
0x18000310e  test    rdx, rdx
0x180003111  jz      short loc_18000311F
0x180003113  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000311a  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000311f  lea     rdi, [rbx+98h]
0x180003126  mov     rsi, [rdi+40h]
0x18000312a  mov     qword ptr [rdi+40h], 0
0x180003132  test    rsi, rsi
0x180003135  jz      short loc_180003157
0x180003137  call    cs:__imp_GetProcessHeap
0x18000313e  nop     dword ptr [rax+rax+00h]
0x180003143  mov     rcx, rax; hHeap
0x180003146  mov     r8, rsi; lpMem
0x180003149  xor     edx, edx; dwFlags
0x18000314b  call    cs:__imp_HeapFree
0x180003152  nop     dword ptr [rax+rax+00h]
0x180003157  mov     rcx, rdi; lpCriticalSection
0x18000315a  call    cs:__imp_DeleteCriticalSection
0x180003161  nop     dword ptr [rax+rax+00h]
0x180003166  mov     rcx, [rbx+90h]; this
0x18000316d  test    rcx, rcx
0x180003170  jz      short loc_180003177
0x180003172  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x180003177  mov     rsi, [rbx+88h]
0x18000317e  mov     qword ptr [rbx+88h], 0
0x180003189  test    rsi, rsi
0x18000318c  jz      short loc_1800031AE
0x18000318e  call    cs:__imp_GetProcessHeap
0x180003195  nop     dword ptr [rax+rax+00h]
0x18000319a  mov     rcx, rax; hHeap
0x18000319d  mov     r8, rsi; lpMem
0x1800031a0  xor     edx, edx; dwFlags
0x1800031a2  call    cs:__imp_HeapFree
0x1800031a9  nop     dword ptr [rax+rax+00h]
0x1800031ae  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800031b2  call    cs:__imp_DeleteCriticalSection
0x1800031b9  nop     dword ptr [rax+rax+00h]
0x1800031be  mov     rdi, [rbx+38h]
0x1800031c2  mov     esi, 1
0x1800031c7  test    rdi, rdi
0x1800031ca  jz      short loc_180003203
0x1800031cc  xor     r9d, r9d; msWindowLength
0x1800031cf  xor     r8d, r8d; msPeriod
0x1800031d2  xor     edx, edx; pftDueTime
0x1800031d4  mov     rcx, rdi; pti
0x1800031d7  call    cs:__imp_SetThreadpoolTimer
0x1800031de  nop     dword ptr [rax+rax+00h]
0x1800031e3  mov     edx, esi; fCancelPendingCallbacks
0x1800031e5  mov     rcx, rdi; pti
0x1800031e8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800031ef  nop     dword ptr [rax+rax+00h]
0x1800031f4  mov     rcx, rdi; pti
0x1800031f7  call    cs:__imp_CloseThreadpoolTimer
0x1800031fe  nop     dword ptr [rax+rax+00h]
0x180003203  mov     rdi, [rbx+30h]
0x180003207  test    rdi, rdi
0x18000320a  jz      short loc_180003244
0x18000320c  xor     r9d, r9d; msWindowLength
0x18000320f  xor     r8d, r8d; msPeriod
0x180003212  xor     edx, edx; pftDueTime
0x180003214  mov     rcx, rdi; pti
0x180003217  call    cs:__imp_SetThreadpoolTimer
0x18000321e  nop     dword ptr [rax+rax+00h]
0x180003223  mov     edx, esi; fCancelPendingCallbacks
0x180003225  mov     rcx, rdi; pti
0x180003228  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000322f  nop     dword ptr [rax+rax+00h]
0x180003234  mov     rcx, rdi; pti
0x180003237  call    cs:__imp_CloseThreadpoolTimer
0x18000323e  nop     dword ptr [rax+rax+00h]
0x180003243  nop
0x180003244  mov     rcx, [rbx+10h]; lpMem
0x180003248  test    rcx, rcx
0x18000324b  jz      short loc_180003253
0x18000324d  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003252  nop
0x180003253  add     rsp, 20h
0x180003257  pop     r15
0x180003259  pop     r14
0x18000325b  pop     rdi
0x18000325c  pop     rsi
0x18000325d  pop     rbx
0x18000325e  retn
```
