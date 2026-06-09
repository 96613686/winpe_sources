# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180024110`
- end: `0x1800242d2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `450`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005e230`

## callees

- `0x180024110`
- `0x180027a5c`
- `0x1800287ac`
- `0x180028820`
- `0x180028f24`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002414f`
- `KERNEL32!GetProcessHeap` at `0x1800241ab`
- `KERNEL32!GetProcessHeap` at `0x180024202`
- `KERNEL32!GetProcessHeap` at `0x18002414f`
- `KERNEL32!GetProcessHeap` at `0x1800241ab`
- `KERNEL32!GetProcessHeap` at `0x180024202`
- `KERNEL32!SetThreadpoolTimer` at `0x18002424b`
- `KERNEL32!SetThreadpoolTimer` at `0x18002428b`
- `KERNEL32!SetThreadpoolTimer` at `0x18002424b`
- `KERNEL32!SetThreadpoolTimer` at `0x18002428b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002426b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800242ab`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002426b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800242ab`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002425c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002429c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002425c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002429c`
- `KERNEL32!HeapFree` at `0x180024163`
- `KERNEL32!HeapFree` at `0x1800241bf`
- `KERNEL32!HeapFree` at `0x180024216`
- `KERNEL32!HeapFree` at `0x180024163`
- `KERNEL32!HeapFree` at `0x1800241bf`
- `KERNEL32!HeapFree` at `0x180024216`
- `KERNEL32!DeleteCriticalSection` at `0x1800241ce`
- `KERNEL32!DeleteCriticalSection` at `0x180024226`
- `KERNEL32!DeleteCriticalSection` at `0x1800241ce`
- `KERNEL32!DeleteCriticalSection` at `0x180024226`

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
  char *v13; // rcx

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
  v13 = (char *)*((_QWORD *)this + 2);
  if ( v13 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v13);
}

```

## disassembly

```asm
0x180024110  push    rbx
0x180024112  push    rsi
0x180024113  push    rdi
0x180024114  push    r14
0x180024116  push    r15
0x180024118  sub     rsp, 20h
0x18002411c  mov     rbx, rcx
0x18002411f  mov     byte ptr [rcx], 0
0x180024122  add     rcx, 30h ; '0'
0x180024126  xor     edx, edx
0x180024128  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002412d  xor     edx, edx
0x18002412f  lea     rcx, [rbx+38h]
0x180024133  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180024138  mov     rdi, [rbx+100h]
0x18002413f  mov     qword ptr [rbx+100h], 0
0x18002414a  test    rdi, rdi
0x18002414d  jz      short loc_18002416F
0x18002414f  call    cs:__imp_GetProcessHeap
0x180024156  nop     dword ptr [rax+rax+00h]
0x18002415b  mov     r8, rdi; lpMem
0x18002415e  xor     edx, edx; dwFlags
0x180024160  mov     rcx, rax; hHeap
0x180024163  call    cs:__imp_HeapFree
0x18002416a  nop     dword ptr [rax+rax+00h]
0x18002416f  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180024176  test    r8, r8
0x180024179  jz      short loc_180024193
0x18002417b  mov     rdx, cs:SRWLock; SRWLock
0x180024182  test    rdx, rdx
0x180024185  jz      short loc_180024193
0x180024187  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18002418e  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180024193  lea     rdi, [rbx+98h]
0x18002419a  mov     rsi, [rdi+40h]
0x18002419e  mov     qword ptr [rdi+40h], 0
0x1800241a6  test    rsi, rsi
0x1800241a9  jz      short loc_1800241CB
0x1800241ab  call    cs:__imp_GetProcessHeap
0x1800241b2  nop     dword ptr [rax+rax+00h]
0x1800241b7  mov     r8, rsi; lpMem
0x1800241ba  xor     edx, edx; dwFlags
0x1800241bc  mov     rcx, rax; hHeap
0x1800241bf  call    cs:__imp_HeapFree
0x1800241c6  nop     dword ptr [rax+rax+00h]
0x1800241cb  mov     rcx, rdi; lpCriticalSection
0x1800241ce  call    cs:__imp_DeleteCriticalSection
0x1800241d5  nop     dword ptr [rax+rax+00h]
0x1800241da  mov     rcx, [rbx+90h]; this
0x1800241e1  test    rcx, rcx
0x1800241e4  jz      short loc_1800241EB
0x1800241e6  call    ?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z; wil::details::UnregisterWilFeatureConfigurationChange(void *)
0x1800241eb  mov     rsi, [rbx+88h]
0x1800241f2  mov     qword ptr [rbx+88h], 0
0x1800241fd  test    rsi, rsi
0x180024200  jz      short loc_180024222
0x180024202  call    cs:__imp_GetProcessHeap
0x180024209  nop     dword ptr [rax+rax+00h]
0x18002420e  mov     r8, rsi; lpMem
0x180024211  xor     edx, edx; dwFlags
0x180024213  mov     rcx, rax; hHeap
0x180024216  call    cs:__imp_HeapFree
0x18002421d  nop     dword ptr [rax+rax+00h]
0x180024222  lea     rcx, [rbx+48h]; lpCriticalSection
0x180024226  call    cs:__imp_DeleteCriticalSection
0x18002422d  nop     dword ptr [rax+rax+00h]
0x180024232  mov     rdi, [rbx+38h]
0x180024236  mov     esi, 1
0x18002423b  test    rdi, rdi
0x18002423e  jz      short loc_180024277
0x180024240  xor     r9d, r9d; msWindowLength
0x180024243  xor     r8d, r8d; msPeriod
0x180024246  xor     edx, edx; pftDueTime
0x180024248  mov     rcx, rdi; pti
0x18002424b  call    cs:__imp_SetThreadpoolTimer
0x180024252  nop     dword ptr [rax+rax+00h]
0x180024257  mov     edx, esi; fCancelPendingCallbacks
0x180024259  mov     rcx, rdi; pti
0x18002425c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180024263  nop     dword ptr [rax+rax+00h]
0x180024268  mov     rcx, rdi; pti
0x18002426b  call    cs:__imp_CloseThreadpoolTimer
0x180024272  nop     dword ptr [rax+rax+00h]
0x180024277  mov     rdi, [rbx+30h]
0x18002427b  test    rdi, rdi
0x18002427e  jz      short loc_1800242B7
0x180024280  xor     r9d, r9d; msWindowLength
0x180024283  xor     r8d, r8d; msPeriod
0x180024286  xor     edx, edx; pftDueTime
0x180024288  mov     rcx, rdi; pti
0x18002428b  call    cs:__imp_SetThreadpoolTimer
0x180024292  nop     dword ptr [rax+rax+00h]
0x180024297  mov     edx, esi; fCancelPendingCallbacks
0x180024299  mov     rcx, rdi; pti
0x18002429c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800242a3  nop     dword ptr [rax+rax+00h]
0x1800242a8  mov     rcx, rdi; pti
0x1800242ab  call    cs:__imp_CloseThreadpoolTimer
0x1800242b2  nop     dword ptr [rax+rax+00h]
0x1800242b7  mov     rcx, [rbx+10h]; lpMem
0x1800242bb  test    rcx, rcx
0x1800242be  jz      short loc_1800242C5
0x1800242c0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800242c5  add     rsp, 20h
0x1800242c9  pop     r15
0x1800242cb  pop     r14
0x1800242cd  pop     rdi
0x1800242ce  pop     rsi
0x1800242cf  pop     rbx
0x1800242d0  retn
```
