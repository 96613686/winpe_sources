# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180009fc0`
- end: `0x18000a105`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006f710`

## callees

- `0x180009fc0`
- `0x18000bcc8`
- `0x18000e9ec`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a02d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a02d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a041`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a041`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a0e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a0e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a0c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a0c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a0d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a0d8`

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
0x180009fc0  mov     [rsp+arg_0], rbx
0x180009fc5  mov     [rsp+arg_8], rsi
0x180009fca  push    rdi
0x180009fcb  sub     rsp, 20h
0x180009fcf  mov     rbx, rcx
0x180009fd2  mov     dword ptr [rcx], 0
0x180009fd8  xor     edx, edx
0x180009fda  add     rcx, 10h
0x180009fde  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009fe3  mov     rcx, rbx; this
0x180009fe6  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180009feb  mov     rdi, [rbx+68h]
0x180009fef  mov     qword ptr [rbx+68h], 0
0x180009ff7  test    rdi, rdi
0x180009ffa  jz      short loc_18000A01C
0x180009ffc  call    cs:__imp_GetProcessHeap
0x18000a003  nop     dword ptr [rax+rax+00h]
0x18000a008  mov     rcx, rax; hHeap
0x18000a00b  mov     r8, rdi; lpMem
0x18000a00e  xor     edx, edx; dwFlags
0x18000a010  call    cs:__imp_HeapFree
0x18000a017  nop     dword ptr [rax+rax+00h]
0x18000a01c  mov     rdi, [rbx+48h]
0x18000a020  mov     qword ptr [rbx+48h], 0
0x18000a028  test    rdi, rdi
0x18000a02b  jz      short loc_18000A04D
0x18000a02d  call    cs:__imp_GetProcessHeap
0x18000a034  nop     dword ptr [rax+rax+00h]
0x18000a039  mov     rcx, rax; hHeap
0x18000a03c  mov     r8, rdi; lpMem
0x18000a03f  xor     edx, edx; dwFlags
0x18000a041  call    cs:__imp_HeapFree
0x18000a048  nop     dword ptr [rax+rax+00h]
0x18000a04d  mov     rcx, [rbx+28h]
0x18000a051  test    rcx, rcx
0x18000a054  jz      short loc_18000A086
0x18000a056  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a05d  test    rax, rax
0x18000a060  jnz     short loc_18000A071
0x18000a062  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a069  test    rdx, rdx
0x18000a06c  jz      short loc_18000A084
0x18000a06e  mov     rax, rdx
0x18000a071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a076  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a07d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a084  jmp     short loc_18000A094
0x18000a086  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000a08d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000a094  mov     rcx, [rbx+20h]
0x18000a098  test    rcx, rcx
0x18000a09b  jz      short loc_18000A0B0
0x18000a09d  test    rax, rax
0x18000a0a0  jnz     short loc_18000A0AA
0x18000a0a2  test    rdx, rdx
0x18000a0a5  jz      short loc_18000A0B0
0x18000a0a7  mov     rax, rdx
0x18000a0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0af  nop
0x18000a0b0  mov     rbx, [rbx+10h]
0x18000a0b4  test    rbx, rbx
0x18000a0b7  jz      short loc_18000A0F4
0x18000a0b9  xor     r9d, r9d; msWindowLength
0x18000a0bc  xor     r8d, r8d; msPeriod
0x18000a0bf  xor     edx, edx; pftDueTime
0x18000a0c1  mov     rcx, rbx; pti
0x18000a0c4  call    cs:__imp_SetThreadpoolTimer
0x18000a0cb  nop     dword ptr [rax+rax+00h]
0x18000a0d0  mov     edx, 1; fCancelPendingCallbacks
0x18000a0d5  mov     rcx, rbx; pti
0x18000a0d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a0df  nop     dword ptr [rax+rax+00h]
0x18000a0e4  mov     rcx, rbx; pti
0x18000a0e7  call    cs:__imp_CloseThreadpoolTimer
0x18000a0ee  nop     dword ptr [rax+rax+00h]
0x18000a0f3  nop
0x18000a0f4  mov     rbx, [rsp+28h+arg_0]
0x18000a0f9  mov     rsi, [rsp+28h+arg_8]
0x18000a0fe  add     rsp, 20h
0x18000a102  pop     rdi
0x18000a103  retn
```
