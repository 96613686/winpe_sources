# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180010e6c`
- end: `0x180010fb1`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018e60`

## callees

- `0x180010e6c`
- `0x1800139fc`
- `0x18001695c`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010ebc`
- `KERNEL32!HeapFree` at `0x180010eed`
- `KERNEL32!HeapFree` at `0x180010ebc`
- `KERNEL32!HeapFree` at `0x180010eed`
- `KERNEL32!GetProcessHeap` at `0x180010ea8`
- `KERNEL32!GetProcessHeap` at `0x180010ed9`
- `KERNEL32!GetProcessHeap` at `0x180010ea8`
- `KERNEL32!GetProcessHeap` at `0x180010ed9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010f84`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010f84`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010f93`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010f93`
- `KERNEL32!SetThreadpoolTimer` at `0x180010f70`
- `KERNEL32!SetThreadpoolTimer` at `0x180010f70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  void (*v6)(void); // rax
  __int64 v7; // rdx
  struct _TP_TIMER *v8; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)this);
  v2 = this[13];
  this[13] = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = this[9];
  this[9] = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  if ( !this[5] )
  {
    v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_12;
  }
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_12;
    v6 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v6();
  v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !this[4] )
    goto LABEL_17;
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_17;
    v6 = (void (*)(void))v7;
  }
  v6();
LABEL_17:
  v8 = this[2];
  if ( v8 )
  {
    SetThreadpoolTimer(v8, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    CloseThreadpoolTimer(v8);
  }
}

```

## disassembly

```asm
0x180010e6c  mov     [rsp+arg_0], rbx
0x180010e71  mov     [rsp+arg_8], rsi
0x180010e76  push    rdi
0x180010e77  sub     rsp, 20h
0x180010e7b  mov     rbx, rcx
0x180010e7e  mov     dword ptr [rcx], 0
0x180010e84  xor     edx, edx
0x180010e86  add     rcx, 10h
0x180010e8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180010e8f  mov     rcx, rbx; this
0x180010e92  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180010e97  mov     rdi, [rbx+68h]
0x180010e9b  mov     qword ptr [rbx+68h], 0
0x180010ea3  test    rdi, rdi
0x180010ea6  jz      short loc_180010EC8
0x180010ea8  call    cs:__imp_GetProcessHeap
0x180010eaf  nop     dword ptr [rax+rax+00h]
0x180010eb4  mov     rcx, rax; hHeap
0x180010eb7  mov     r8, rdi; lpMem
0x180010eba  xor     edx, edx; dwFlags
0x180010ebc  call    cs:__imp_HeapFree
0x180010ec3  nop     dword ptr [rax+rax+00h]
0x180010ec8  mov     rdi, [rbx+48h]
0x180010ecc  mov     qword ptr [rbx+48h], 0
0x180010ed4  test    rdi, rdi
0x180010ed7  jz      short loc_180010EF9
0x180010ed9  call    cs:__imp_GetProcessHeap
0x180010ee0  nop     dword ptr [rax+rax+00h]
0x180010ee5  mov     rcx, rax; hHeap
0x180010ee8  mov     r8, rdi; lpMem
0x180010eeb  xor     edx, edx; dwFlags
0x180010eed  call    cs:__imp_HeapFree
0x180010ef4  nop     dword ptr [rax+rax+00h]
0x180010ef9  mov     rcx, [rbx+28h]
0x180010efd  test    rcx, rcx
0x180010f00  jz      short loc_180010F32
0x180010f02  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010f09  test    rax, rax
0x180010f0c  jnz     short loc_180010F1D
0x180010f0e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010f15  test    rdx, rdx
0x180010f18  jz      short loc_180010F30
0x180010f1a  mov     rax, rdx
0x180010f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f22  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010f29  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010f30  jmp     short loc_180010F40
0x180010f32  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010f39  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010f40  mov     rcx, [rbx+20h]
0x180010f44  test    rcx, rcx
0x180010f47  jz      short loc_180010F5C
0x180010f49  test    rax, rax
0x180010f4c  jnz     short loc_180010F56
0x180010f4e  test    rdx, rdx
0x180010f51  jz      short loc_180010F5C
0x180010f53  mov     rax, rdx
0x180010f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f5b  nop
0x180010f5c  mov     rbx, [rbx+10h]
0x180010f60  test    rbx, rbx
0x180010f63  jz      short loc_180010FA0
0x180010f65  xor     r9d, r9d; msWindowLength
0x180010f68  xor     r8d, r8d; msPeriod
0x180010f6b  xor     edx, edx; pftDueTime
0x180010f6d  mov     rcx, rbx; pti
0x180010f70  call    cs:__imp_SetThreadpoolTimer
0x180010f77  nop     dword ptr [rax+rax+00h]
0x180010f7c  mov     edx, 1; fCancelPendingCallbacks
0x180010f81  mov     rcx, rbx; pti
0x180010f84  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010f8b  nop     dword ptr [rax+rax+00h]
0x180010f90  mov     rcx, rbx; pti
0x180010f93  call    cs:__imp_CloseThreadpoolTimer
0x180010f9a  nop     dword ptr [rax+rax+00h]
0x180010f9f  nop
0x180010fa0  mov     rbx, [rsp+28h+arg_0]
0x180010fa5  mov     rsi, [rsp+28h+arg_8]
0x180010faa  add     rsp, 20h
0x180010fae  pop     rdi
0x180010faf  retn
```
