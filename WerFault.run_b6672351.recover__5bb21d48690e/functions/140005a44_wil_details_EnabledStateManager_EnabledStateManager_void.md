# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140005a44`
- end: `0x140005b89`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140060550`

## callees

- `0x140005a44`
- `0x140008da8`
- `0x14000cec8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ac5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005a94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005ab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005a80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005ab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005b6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005b6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005b5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005b5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005b48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005b48`

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
0x140005a44  mov     [rsp+arg_0], rbx
0x140005a49  mov     [rsp+arg_8], rsi
0x140005a4e  push    rdi
0x140005a4f  sub     rsp, 20h
0x140005a53  mov     rbx, rcx
0x140005a56  mov     dword ptr [rcx], 0
0x140005a5c  xor     edx, edx
0x140005a5e  add     rcx, 10h
0x140005a62  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140005a67  mov     rcx, rbx; this
0x140005a6a  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140005a6f  mov     rdi, [rbx+68h]
0x140005a73  mov     qword ptr [rbx+68h], 0
0x140005a7b  test    rdi, rdi
0x140005a7e  jz      short loc_140005AA0
0x140005a80  call    cs:__imp_GetProcessHeap
0x140005a87  nop     dword ptr [rax+rax+00h]
0x140005a8c  mov     rcx, rax; hHeap
0x140005a8f  mov     r8, rdi; lpMem
0x140005a92  xor     edx, edx; dwFlags
0x140005a94  call    cs:__imp_HeapFree
0x140005a9b  nop     dword ptr [rax+rax+00h]
0x140005aa0  mov     rdi, [rbx+48h]
0x140005aa4  mov     qword ptr [rbx+48h], 0
0x140005aac  test    rdi, rdi
0x140005aaf  jz      short loc_140005AD1
0x140005ab1  call    cs:__imp_GetProcessHeap
0x140005ab8  nop     dword ptr [rax+rax+00h]
0x140005abd  mov     rcx, rax; hHeap
0x140005ac0  mov     r8, rdi; lpMem
0x140005ac3  xor     edx, edx; dwFlags
0x140005ac5  call    cs:__imp_HeapFree
0x140005acc  nop     dword ptr [rax+rax+00h]
0x140005ad1  mov     rcx, [rbx+28h]
0x140005ad5  test    rcx, rcx
0x140005ad8  jz      short loc_140005B0A
0x140005ada  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005ae1  test    rax, rax
0x140005ae4  jnz     short loc_140005AF5
0x140005ae6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005aed  test    rdx, rdx
0x140005af0  jz      short loc_140005B08
0x140005af2  mov     rax, rdx
0x140005af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005afa  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005b01  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005b08  jmp     short loc_140005B18
0x140005b0a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140005b11  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140005b18  mov     rcx, [rbx+20h]
0x140005b1c  test    rcx, rcx
0x140005b1f  jz      short loc_140005B34
0x140005b21  test    rax, rax
0x140005b24  jnz     short loc_140005B2E
0x140005b26  test    rdx, rdx
0x140005b29  jz      short loc_140005B34
0x140005b2b  mov     rax, rdx
0x140005b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b33  nop
0x140005b34  mov     rbx, [rbx+10h]
0x140005b38  test    rbx, rbx
0x140005b3b  jz      short loc_140005B78
0x140005b3d  xor     r9d, r9d; msWindowLength
0x140005b40  xor     r8d, r8d; msPeriod
0x140005b43  xor     edx, edx; pftDueTime
0x140005b45  mov     rcx, rbx; pti
0x140005b48  call    cs:__imp_SetThreadpoolTimer
0x140005b4f  nop     dword ptr [rax+rax+00h]
0x140005b54  mov     edx, 1; fCancelPendingCallbacks
0x140005b59  mov     rcx, rbx; pti
0x140005b5c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005b63  nop     dword ptr [rax+rax+00h]
0x140005b68  mov     rcx, rbx; pti
0x140005b6b  call    cs:__imp_CloseThreadpoolTimer
0x140005b72  nop     dword ptr [rax+rax+00h]
0x140005b77  nop
0x140005b78  mov     rbx, [rsp+28h+arg_0]
0x140005b7d  mov     rsi, [rsp+28h+arg_8]
0x140005b82  add     rsp, 20h
0x140005b86  pop     rdi
0x140005b87  retn
```
