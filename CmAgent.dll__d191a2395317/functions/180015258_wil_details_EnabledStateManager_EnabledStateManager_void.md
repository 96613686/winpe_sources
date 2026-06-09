# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180015258`
- end: `0x18001539d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(struct _TP_TIMER **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180037010`

## callees

- `0x180015258`
- `0x18001956c`
- `0x180021b48`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001530b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001533c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001530b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001533c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015370`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015370`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001537f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001537f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001535c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001535c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  void (*v2)(void); // rax
  __int64 v3; // rdx
  struct _TP_TIMER *v4; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v6; // rdi
  HANDLE v7; // rax
  struct _TP_TIMER *v8; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)this);
  if ( !this[13] )
  {
    v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_8;
  }
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_8;
    v2 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v2();
  v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_8:
  if ( !this[12] )
    goto LABEL_13;
  if ( !v2 )
  {
    if ( !v3 )
      goto LABEL_13;
    v2 = (void (*)(void))v3;
  }
  v2();
LABEL_13:
  v4 = this[11];
  this[11] = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = this[7];
  this[7] = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
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
0x180015258  mov     [rsp+arg_0], rbx
0x18001525d  mov     [rsp+arg_8], rsi
0x180015262  push    rdi
0x180015263  sub     rsp, 20h
0x180015267  mov     rbx, rcx
0x18001526a  mov     dword ptr [rcx], 0
0x180015270  xor     edx, edx
0x180015272  add     rcx, 10h
0x180015276  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001527b  mov     rcx, rbx; this
0x18001527e  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180015283  mov     rcx, [rbx+68h]
0x180015287  test    rcx, rcx
0x18001528a  jz      short loc_1800152BC
0x18001528c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180015293  test    rax, rax
0x180015296  jnz     short loc_1800152A7
0x180015298  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001529f  test    rdx, rdx
0x1800152a2  jz      short loc_1800152BA
0x1800152a4  mov     rax, rdx
0x1800152a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ac  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800152b3  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800152ba  jmp     short loc_1800152CA
0x1800152bc  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800152c3  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800152ca  mov     rcx, [rbx+60h]
0x1800152ce  test    rcx, rcx
0x1800152d1  jz      short loc_1800152E6
0x1800152d3  test    rax, rax
0x1800152d6  jnz     short loc_1800152E0
0x1800152d8  test    rdx, rdx
0x1800152db  jz      short loc_1800152E6
0x1800152dd  mov     rax, rdx
0x1800152e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152e5  nop
0x1800152e6  mov     rdi, [rbx+58h]
0x1800152ea  mov     qword ptr [rbx+58h], 0
0x1800152f2  test    rdi, rdi
0x1800152f5  jz      short loc_180015317
0x1800152f7  call    cs:__imp_GetProcessHeap
0x1800152fe  nop     dword ptr [rax+rax+00h]
0x180015303  mov     rcx, rax; hHeap
0x180015306  mov     r8, rdi; lpMem
0x180015309  xor     edx, edx; dwFlags
0x18001530b  call    cs:__imp_HeapFree
0x180015312  nop     dword ptr [rax+rax+00h]
0x180015317  mov     rdi, [rbx+38h]
0x18001531b  mov     qword ptr [rbx+38h], 0
0x180015323  test    rdi, rdi
0x180015326  jz      short loc_180015348
0x180015328  call    cs:__imp_GetProcessHeap
0x18001532f  nop     dword ptr [rax+rax+00h]
0x180015334  mov     rcx, rax; hHeap
0x180015337  mov     r8, rdi; lpMem
0x18001533a  xor     edx, edx; dwFlags
0x18001533c  call    cs:__imp_HeapFree
0x180015343  nop     dword ptr [rax+rax+00h]
0x180015348  mov     rbx, [rbx+10h]
0x18001534c  test    rbx, rbx
0x18001534f  jz      short loc_18001538C
0x180015351  xor     r9d, r9d; msWindowLength
0x180015354  xor     r8d, r8d; msPeriod
0x180015357  xor     edx, edx; pftDueTime
0x180015359  mov     rcx, rbx; pti
0x18001535c  call    cs:__imp_SetThreadpoolTimer
0x180015363  nop     dword ptr [rax+rax+00h]
0x180015368  mov     edx, 1; fCancelPendingCallbacks
0x18001536d  mov     rcx, rbx; pti
0x180015370  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015377  nop     dword ptr [rax+rax+00h]
0x18001537c  mov     rcx, rbx; pti
0x18001537f  call    cs:__imp_CloseThreadpoolTimer
0x180015386  nop     dword ptr [rax+rax+00h]
0x18001538b  nop
0x18001538c  mov     rbx, [rsp+28h+arg_0]
0x180015391  mov     rsi, [rsp+28h+arg_8]
0x180015396  add     rsp, 20h
0x18001539a  pop     rdi
0x18001539b  retn
```
