# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180006578`
- end: `0x1800066c7`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `335`
- prototype: `void __fastcall(struct _TP_TIMER **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801c9960`

## callees

- `0x180006578`
- `0x180009b24`
- `0x18000d194`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1800066a9`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800066a9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000669a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000669a`
- `KERNEL32!SetThreadpoolTimer` at `0x180006686`
- `KERNEL32!SetThreadpoolTimer` at `0x180006686`
- `KERNEL32!GetProcessHeap` at `0x1800065be`
- `KERNEL32!GetProcessHeap` at `0x1800065ef`
- `KERNEL32!GetProcessHeap` at `0x1800065be`
- `KERNEL32!GetProcessHeap` at `0x1800065ef`
- `KERNEL32!HeapFree` at `0x1800065d2`
- `KERNEL32!HeapFree` at `0x180006603`
- `KERNEL32!HeapFree` at `0x1800065d2`
- `KERNEL32!HeapFree` at `0x180006603`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  struct _TP_TIMER *v6; // rcx
  void (__fastcall *v7)(struct _TP_TIMER *); // rax
  __int64 v8; // rdx
  struct _TP_TIMER *v9; // rcx
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  wil::details::EnabledStateManager::ProcessShutdown((RTL_SRWLOCK *)this);
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
  v6 = this[5];
  if ( !v6 )
  {
    v7 = (void (__fastcall *)(struct _TP_TIMER *))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v8 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_12;
  }
  v7 = (void (__fastcall *)(struct _TP_TIMER *))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v8 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_12;
    v7 = (void (__fastcall *)(struct _TP_TIMER *))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v7(v6);
  v8 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v7 = (void (__fastcall *)(struct _TP_TIMER *))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  v9 = this[4];
  if ( !v9 )
    goto LABEL_17;
  if ( !v7 )
  {
    if ( !v8 )
      goto LABEL_17;
    v7 = (void (__fastcall *)(struct _TP_TIMER *))v8;
  }
  v7(v9);
LABEL_17:
  v10 = this[2];
  if ( v10 )
  {
    SetThreadpoolTimer(v10, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x180006578  push    rdi
0x18000657a  sub     rsp, 30h
0x18000657e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180006587  mov     [rsp+38h+arg_0], rbx
0x18000658c  mov     [rsp+38h+arg_8], rsi
0x180006591  mov     rbx, rcx
0x180006594  mov     dword ptr [rcx], 0
0x18000659a  xor     edx, edx
0x18000659c  add     rcx, 10h
0x1800065a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800065a5  mov     rcx, rbx; this
0x1800065a8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800065ad  mov     rdi, [rbx+68h]
0x1800065b1  mov     qword ptr [rbx+68h], 0
0x1800065b9  test    rdi, rdi
0x1800065bc  jz      short loc_1800065DE
0x1800065be  call    cs:__imp_GetProcessHeap
0x1800065c5  nop     dword ptr [rax+rax+00h]
0x1800065ca  mov     rcx, rax; hHeap
0x1800065cd  mov     r8, rdi; lpMem
0x1800065d0  xor     edx, edx; dwFlags
0x1800065d2  call    cs:__imp_HeapFree
0x1800065d9  nop     dword ptr [rax+rax+00h]
0x1800065de  mov     rdi, [rbx+48h]
0x1800065e2  mov     qword ptr [rbx+48h], 0
0x1800065ea  test    rdi, rdi
0x1800065ed  jz      short loc_18000660F
0x1800065ef  call    cs:__imp_GetProcessHeap
0x1800065f6  nop     dword ptr [rax+rax+00h]
0x1800065fb  mov     rcx, rax; hHeap
0x1800065fe  mov     r8, rdi; lpMem
0x180006601  xor     edx, edx; dwFlags
0x180006603  call    cs:__imp_HeapFree
0x18000660a  nop     dword ptr [rax+rax+00h]
0x18000660f  mov     rcx, [rbx+28h]
0x180006613  test    rcx, rcx
0x180006616  jz      short loc_180006648
0x180006618  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000661f  test    rax, rax
0x180006622  jnz     short loc_180006633
0x180006624  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000662b  test    rdx, rdx
0x18000662e  jz      short loc_180006646
0x180006630  mov     rax, rdx
0x180006633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006638  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000663f  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180006646  jmp     short loc_180006656
0x180006648  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000664f  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180006656  mov     rcx, [rbx+20h]
0x18000665a  test    rcx, rcx
0x18000665d  jz      short loc_180006672
0x18000665f  test    rax, rax
0x180006662  jnz     short loc_18000666C
0x180006664  test    rdx, rdx
0x180006667  jz      short loc_180006672
0x180006669  mov     rax, rdx
0x18000666c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006671  nop
0x180006672  mov     rbx, [rbx+10h]
0x180006676  test    rbx, rbx
0x180006679  jz      short loc_1800066B6
0x18000667b  xor     r9d, r9d; msWindowLength
0x18000667e  xor     r8d, r8d; msPeriod
0x180006681  xor     edx, edx; pftDueTime
0x180006683  mov     rcx, rbx; pti
0x180006686  call    cs:__imp_SetThreadpoolTimer
0x18000668d  nop     dword ptr [rax+rax+00h]
0x180006692  mov     edx, 1; fCancelPendingCallbacks
0x180006697  mov     rcx, rbx; pti
0x18000669a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800066a1  nop     dword ptr [rax+rax+00h]
0x1800066a6  mov     rcx, rbx; pti
0x1800066a9  call    cs:__imp_CloseThreadpoolTimer
0x1800066b0  nop     dword ptr [rax+rax+00h]
0x1800066b5  nop
0x1800066b6  mov     rbx, [rsp+38h+arg_0]
0x1800066bb  mov     rsi, [rsp+38h+arg_8]
0x1800066c0  add     rsp, 30h
0x1800066c4  pop     rdi
0x1800066c5  retn
```
