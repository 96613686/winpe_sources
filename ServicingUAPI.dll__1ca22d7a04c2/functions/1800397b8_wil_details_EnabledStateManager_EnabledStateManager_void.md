# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800397b8`
- end: `0x1800398eb`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `307`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1801b82b0`

## callees

- `0x1800397b8`
- `0x18003a898`
- `0x18003c954`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003985a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003988b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003985a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003988b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039846`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039877`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039846`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039877`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800398ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800398ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800398bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800398bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800398ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800398ce`

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
  v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( this[13] )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_7;
      v2 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v2();
    v2 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v3 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_7:
  if ( !this[12] )
    goto LABEL_12;
  if ( !v2 )
  {
    if ( !v3 )
      goto LABEL_12;
    v2 = (void (*)(void))v3;
  }
  v2();
LABEL_12:
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
0x1800397b8  mov     [rsp+arg_0], rbx
0x1800397bd  mov     [rsp+arg_8], rsi
0x1800397c2  push    rdi
0x1800397c3  sub     rsp, 20h
0x1800397c7  mov     rbx, rcx
0x1800397ca  mov     dword ptr [rcx], 0
0x1800397d0  add     rcx, 10h
0x1800397d4  xor     edx, edx
0x1800397d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800397db  mov     rcx, rbx; this
0x1800397de  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800397e3  mov     rcx, [rbx+68h]
0x1800397e7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800397ee  test    rcx, rcx
0x1800397f1  jz      short loc_180039813
0x1800397f3  test    rax, rax
0x1800397f6  jnz     short loc_180039807
0x1800397f8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800397ff  test    rdx, rdx
0x180039802  jz      short loc_18003981A
0x180039804  mov     rax, rdx
0x180039807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003980c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180039813  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18003981a  mov     rcx, [rbx+60h]
0x18003981e  test    rcx, rcx
0x180039821  jz      short loc_180039835
0x180039823  test    rax, rax
0x180039826  jnz     short loc_180039830
0x180039828  test    rdx, rdx
0x18003982b  jz      short loc_180039835
0x18003982d  mov     rax, rdx
0x180039830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039835  mov     rdi, [rbx+58h]
0x180039839  mov     qword ptr [rbx+58h], 0
0x180039841  test    rdi, rdi
0x180039844  jz      short loc_180039866
0x180039846  call    cs:__imp_GetProcessHeap
0x18003984d  nop     dword ptr [rax+rax+00h]
0x180039852  mov     r8, rdi; lpMem
0x180039855  xor     edx, edx; dwFlags
0x180039857  mov     rcx, rax; hHeap
0x18003985a  call    cs:__imp_HeapFree
0x180039861  nop     dword ptr [rax+rax+00h]
0x180039866  mov     rdi, [rbx+38h]
0x18003986a  mov     qword ptr [rbx+38h], 0
0x180039872  test    rdi, rdi
0x180039875  jz      short loc_180039897
0x180039877  call    cs:__imp_GetProcessHeap
0x18003987e  nop     dword ptr [rax+rax+00h]
0x180039883  mov     r8, rdi; lpMem
0x180039886  xor     edx, edx; dwFlags
0x180039888  mov     rcx, rax; hHeap
0x18003988b  call    cs:__imp_HeapFree
0x180039892  nop     dword ptr [rax+rax+00h]
0x180039897  mov     rbx, [rbx+10h]
0x18003989b  test    rbx, rbx
0x18003989e  jz      short loc_1800398DA
0x1800398a0  xor     r9d, r9d; msWindowLength
0x1800398a3  xor     r8d, r8d; msPeriod
0x1800398a6  xor     edx, edx; pftDueTime
0x1800398a8  mov     rcx, rbx; pti
0x1800398ab  call    cs:__imp_SetThreadpoolTimer
0x1800398b2  nop     dword ptr [rax+rax+00h]
0x1800398b7  mov     edx, 1; fCancelPendingCallbacks
0x1800398bc  mov     rcx, rbx; pti
0x1800398bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800398c6  nop     dword ptr [rax+rax+00h]
0x1800398cb  mov     rcx, rbx; pti
0x1800398ce  call    cs:__imp_CloseThreadpoolTimer
0x1800398d5  nop     dword ptr [rax+rax+00h]
0x1800398da  mov     rbx, [rsp+28h+arg_0]
0x1800398df  mov     rsi, [rsp+28h+arg_8]
0x1800398e4  add     rsp, 20h
0x1800398e8  pop     rdi
0x1800398e9  retn
```
