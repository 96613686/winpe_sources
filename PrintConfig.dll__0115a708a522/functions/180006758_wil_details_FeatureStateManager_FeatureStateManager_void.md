# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180006758`
- end: `0x180006925`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `461`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1801c99c0`

## callees

- `0x180006758`
- `0x18000b104`
- `0x18000c774`
- `0x18000c7e8`
- `0x18000d194`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1800068bc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068fc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068bc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800068fc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068ad`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068ed`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068ad`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800068ed`
- `KERNEL32!SetThreadpoolTimer` at `0x18000689c`
- `KERNEL32!SetThreadpoolTimer` at `0x1800068dc`
- `KERNEL32!SetThreadpoolTimer` at `0x18000689c`
- `KERNEL32!SetThreadpoolTimer` at `0x1800068dc`
- `KERNEL32!GetProcessHeap` at `0x1800067a0`
- `KERNEL32!GetProcessHeap` at `0x1800067fc`
- `KERNEL32!GetProcessHeap` at `0x180006853`
- `KERNEL32!GetProcessHeap` at `0x1800067a0`
- `KERNEL32!GetProcessHeap` at `0x1800067fc`
- `KERNEL32!GetProcessHeap` at `0x180006853`
- `KERNEL32!HeapFree` at `0x1800067b4`
- `KERNEL32!HeapFree` at `0x180006810`
- `KERNEL32!HeapFree` at `0x180006867`
- `KERNEL32!HeapFree` at `0x1800067b4`
- `KERNEL32!HeapFree` at `0x180006810`
- `KERNEL32!HeapFree` at `0x180006867`
- `KERNEL32!DeleteCriticalSection` at `0x18000681f`
- `KERNEL32!DeleteCriticalSection` at `0x180006877`
- `KERNEL32!DeleteCriticalSection` at `0x18000681f`
- `KERNEL32!DeleteCriticalSection` at `0x180006877`

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
  _QWORD *v13; // rcx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (struct _TP_TIMER **)this + 6,
    0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (struct _TP_TIMER **)this + 7,
    0);
  v2 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v4 && qword_180293978 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180293978[25], qword_180293978, v4);
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
  v13 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x180006758  push    rbx
0x18000675a  push    rsi
0x18000675b  push    rdi
0x18000675c  push    r14
0x18000675e  push    r15
0x180006760  sub     rsp, 30h
0x180006764  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000676d  mov     rbx, rcx
0x180006770  mov     byte ptr [rcx], 0
0x180006773  xor     edx, edx
0x180006775  add     rcx, 30h ; '0'
0x180006779  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000677e  xor     edx, edx
0x180006780  lea     rcx, [rbx+38h]
0x180006784  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006789  mov     rdi, [rbx+100h]
0x180006790  mov     qword ptr [rbx+100h], 0
0x18000679b  test    rdi, rdi
0x18000679e  jz      short loc_1800067C0
0x1800067a0  call    cs:__imp_GetProcessHeap
0x1800067a7  nop     dword ptr [rax+rax+00h]
0x1800067ac  mov     rcx, rax; hHeap
0x1800067af  mov     r8, rdi; lpMem
0x1800067b2  xor     edx, edx; dwFlags
0x1800067b4  call    cs:__imp_HeapFree
0x1800067bb  nop     dword ptr [rax+rax+00h]
0x1800067c0  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800067c7  test    r8, r8
0x1800067ca  jz      short loc_1800067E4
0x1800067cc  mov     rdx, cs:qword_180293978; SRWLock
0x1800067d3  test    rdx, rdx
0x1800067d6  jz      short loc_1800067E4
0x1800067d8  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800067df  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800067e4  lea     rdi, [rbx+98h]
0x1800067eb  mov     rsi, [rdi+40h]
0x1800067ef  mov     qword ptr [rdi+40h], 0
0x1800067f7  test    rsi, rsi
0x1800067fa  jz      short loc_18000681C
0x1800067fc  call    cs:__imp_GetProcessHeap
0x180006803  nop     dword ptr [rax+rax+00h]
0x180006808  mov     rcx, rax; hHeap
0x18000680b  mov     r8, rsi; lpMem
0x18000680e  xor     edx, edx; dwFlags
0x180006810  call    cs:__imp_HeapFree
0x180006817  nop     dword ptr [rax+rax+00h]
0x18000681c  mov     rcx, rdi; lpCriticalSection
0x18000681f  call    cs:__imp_DeleteCriticalSection
0x180006826  nop     dword ptr [rax+rax+00h]
0x18000682b  mov     rcx, [rbx+90h]; this
0x180006832  test    rcx, rcx
0x180006835  jz      short loc_18000683C
0x180006837  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x18000683c  mov     rsi, [rbx+88h]
0x180006843  mov     qword ptr [rbx+88h], 0
0x18000684e  test    rsi, rsi
0x180006851  jz      short loc_180006873
0x180006853  call    cs:__imp_GetProcessHeap
0x18000685a  nop     dword ptr [rax+rax+00h]
0x18000685f  mov     rcx, rax; hHeap
0x180006862  mov     r8, rsi; lpMem
0x180006865  xor     edx, edx; dwFlags
0x180006867  call    cs:__imp_HeapFree
0x18000686e  nop     dword ptr [rax+rax+00h]
0x180006873  lea     rcx, [rbx+48h]; lpCriticalSection
0x180006877  call    cs:__imp_DeleteCriticalSection
0x18000687e  nop     dword ptr [rax+rax+00h]
0x180006883  mov     rdi, [rbx+38h]
0x180006887  mov     esi, 1
0x18000688c  test    rdi, rdi
0x18000688f  jz      short loc_1800068C8
0x180006891  xor     r9d, r9d; msWindowLength
0x180006894  xor     r8d, r8d; msPeriod
0x180006897  xor     edx, edx; pftDueTime
0x180006899  mov     rcx, rdi; pti
0x18000689c  call    cs:__imp_SetThreadpoolTimer
0x1800068a3  nop     dword ptr [rax+rax+00h]
0x1800068a8  mov     edx, esi; fCancelPendingCallbacks
0x1800068aa  mov     rcx, rdi; pti
0x1800068ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068b4  nop     dword ptr [rax+rax+00h]
0x1800068b9  mov     rcx, rdi; pti
0x1800068bc  call    cs:__imp_CloseThreadpoolTimer
0x1800068c3  nop     dword ptr [rax+rax+00h]
0x1800068c8  mov     rdi, [rbx+30h]
0x1800068cc  test    rdi, rdi
0x1800068cf  jz      short loc_180006909
0x1800068d1  xor     r9d, r9d; msWindowLength
0x1800068d4  xor     r8d, r8d; msPeriod
0x1800068d7  xor     edx, edx; pftDueTime
0x1800068d9  mov     rcx, rdi; pti
0x1800068dc  call    cs:__imp_SetThreadpoolTimer
0x1800068e3  nop     dword ptr [rax+rax+00h]
0x1800068e8  mov     edx, esi; fCancelPendingCallbacks
0x1800068ea  mov     rcx, rdi; pti
0x1800068ed  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800068f4  nop     dword ptr [rax+rax+00h]
0x1800068f9  mov     rcx, rdi; pti
0x1800068fc  call    cs:__imp_CloseThreadpoolTimer
0x180006903  nop     dword ptr [rax+rax+00h]
0x180006908  nop
0x180006909  mov     rcx, [rbx+10h]; lpMem
0x18000690d  test    rcx, rcx
0x180006910  jz      short loc_180006918
0x180006912  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180006917  nop
0x180006918  add     rsp, 30h
0x18000691c  pop     r15
0x18000691e  pop     r14
0x180006920  pop     rdi
0x180006921  pop     rsi
0x180006922  pop     rbx
0x180006923  retn
```
