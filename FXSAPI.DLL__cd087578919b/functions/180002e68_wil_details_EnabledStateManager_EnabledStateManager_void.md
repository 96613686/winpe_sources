# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180002e68`
- end: `0x180002fad`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003d990`

## callees

- `0x180002e68`
- `0x180006528`
- `0x18000981c`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002ea4`
- `KERNEL32!GetProcessHeap` at `0x180002ed5`
- `KERNEL32!GetProcessHeap` at `0x180002ea4`
- `KERNEL32!GetProcessHeap` at `0x180002ed5`
- `KERNEL32!CloseThreadpoolTimer` at `0x180002f8f`
- `KERNEL32!CloseThreadpoolTimer` at `0x180002f8f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180002f80`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180002f80`
- `KERNEL32!SetThreadpoolTimer` at `0x180002f6c`
- `KERNEL32!SetThreadpoolTimer` at `0x180002f6c`
- `KERNEL32!HeapFree` at `0x180002eb8`
- `KERNEL32!HeapFree` at `0x180002ee9`
- `KERNEL32!HeapFree` at `0x180002eb8`
- `KERNEL32!HeapFree` at `0x180002ee9`

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
0x180002e68  mov     [rsp+arg_0], rbx
0x180002e6d  mov     [rsp+arg_8], rsi
0x180002e72  push    rdi
0x180002e73  sub     rsp, 20h
0x180002e77  mov     rbx, rcx
0x180002e7a  mov     dword ptr [rcx], 0
0x180002e80  xor     edx, edx
0x180002e82  add     rcx, 10h
0x180002e86  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180002e8b  mov     rcx, rbx; this
0x180002e8e  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180002e93  mov     rdi, [rbx+68h]
0x180002e97  mov     qword ptr [rbx+68h], 0
0x180002e9f  test    rdi, rdi
0x180002ea2  jz      short loc_180002EC4
0x180002ea4  call    cs:__imp_GetProcessHeap
0x180002eab  nop     dword ptr [rax+rax+00h]
0x180002eb0  mov     rcx, rax; hHeap
0x180002eb3  mov     r8, rdi; lpMem
0x180002eb6  xor     edx, edx; dwFlags
0x180002eb8  call    cs:__imp_HeapFree
0x180002ebf  nop     dword ptr [rax+rax+00h]
0x180002ec4  mov     rdi, [rbx+48h]
0x180002ec8  mov     qword ptr [rbx+48h], 0
0x180002ed0  test    rdi, rdi
0x180002ed3  jz      short loc_180002EF5
0x180002ed5  call    cs:__imp_GetProcessHeap
0x180002edc  nop     dword ptr [rax+rax+00h]
0x180002ee1  mov     rcx, rax; hHeap
0x180002ee4  mov     r8, rdi; lpMem
0x180002ee7  xor     edx, edx; dwFlags
0x180002ee9  call    cs:__imp_HeapFree
0x180002ef0  nop     dword ptr [rax+rax+00h]
0x180002ef5  mov     rcx, [rbx+28h]
0x180002ef9  test    rcx, rcx
0x180002efc  jz      short loc_180002F2E
0x180002efe  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180002f05  test    rax, rax
0x180002f08  jnz     short loc_180002F19
0x180002f0a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180002f11  test    rdx, rdx
0x180002f14  jz      short loc_180002F2C
0x180002f16  mov     rax, rdx
0x180002f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180002f25  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180002f2c  jmp     short loc_180002F3C
0x180002f2e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180002f35  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180002f3c  mov     rcx, [rbx+20h]
0x180002f40  test    rcx, rcx
0x180002f43  jz      short loc_180002F58
0x180002f45  test    rax, rax
0x180002f48  jnz     short loc_180002F52
0x180002f4a  test    rdx, rdx
0x180002f4d  jz      short loc_180002F58
0x180002f4f  mov     rax, rdx
0x180002f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f57  nop
0x180002f58  mov     rbx, [rbx+10h]
0x180002f5c  test    rbx, rbx
0x180002f5f  jz      short loc_180002F9C
0x180002f61  xor     r9d, r9d; msWindowLength
0x180002f64  xor     r8d, r8d; msPeriod
0x180002f67  xor     edx, edx; pftDueTime
0x180002f69  mov     rcx, rbx; pti
0x180002f6c  call    cs:__imp_SetThreadpoolTimer
0x180002f73  nop     dword ptr [rax+rax+00h]
0x180002f78  mov     edx, 1; fCancelPendingCallbacks
0x180002f7d  mov     rcx, rbx; pti
0x180002f80  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002f87  nop     dword ptr [rax+rax+00h]
0x180002f8c  mov     rcx, rbx; pti
0x180002f8f  call    cs:__imp_CloseThreadpoolTimer
0x180002f96  nop     dword ptr [rax+rax+00h]
0x180002f9b  nop
0x180002f9c  mov     rbx, [rsp+28h+arg_0]
0x180002fa1  mov     rsi, [rsp+28h+arg_8]
0x180002fa6  add     rsp, 20h
0x180002faa  pop     rdi
0x180002fab  retn
```
