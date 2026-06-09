# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000ae14`
- end: `0x18000af59`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(struct _TP_TIMER **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e140`

## callees

- `0x18000ae14`
- `0x18000e870`
- `0x1800125b8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae95`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af2c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af18`

## pseudocode

```c
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
0x18000ae14  mov     [rsp+arg_0], rbx
0x18000ae19  mov     [rsp+arg_8], rsi
0x18000ae1e  push    rdi
0x18000ae1f  sub     rsp, 20h
0x18000ae23  mov     rbx, rcx
0x18000ae26  mov     dword ptr [rcx], 0
0x18000ae2c  xor     edx, edx
0x18000ae2e  add     rcx, 10h
0x18000ae32  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ae37  mov     rcx, rbx; this
0x18000ae3a  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000ae3f  mov     rdi, [rbx+68h]
0x18000ae43  mov     qword ptr [rbx+68h], 0
0x18000ae4b  test    rdi, rdi
0x18000ae4e  jz      short loc_18000AE70
0x18000ae50  call    cs:__imp_GetProcessHeap
0x18000ae57  nop     dword ptr [rax+rax+00h]
0x18000ae5c  mov     rcx, rax; hHeap
0x18000ae5f  mov     r8, rdi; lpMem
0x18000ae62  xor     edx, edx; dwFlags
0x18000ae64  call    cs:__imp_HeapFree
0x18000ae6b  nop     dword ptr [rax+rax+00h]
0x18000ae70  mov     rdi, [rbx+48h]
0x18000ae74  mov     qword ptr [rbx+48h], 0
0x18000ae7c  test    rdi, rdi
0x18000ae7f  jz      short loc_18000AEA1
0x18000ae81  call    cs:__imp_GetProcessHeap
0x18000ae88  nop     dword ptr [rax+rax+00h]
0x18000ae8d  mov     rcx, rax; hHeap
0x18000ae90  mov     r8, rdi; lpMem
0x18000ae93  xor     edx, edx; dwFlags
0x18000ae95  call    cs:__imp_HeapFree
0x18000ae9c  nop     dword ptr [rax+rax+00h]
0x18000aea1  mov     rcx, [rbx+28h]
0x18000aea5  test    rcx, rcx
0x18000aea8  jz      short loc_18000AEDA
0x18000aeaa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000aeb1  test    rax, rax
0x18000aeb4  jnz     short loc_18000AEC5
0x18000aeb6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000aebd  test    rdx, rdx
0x18000aec0  jz      short loc_18000AED8
0x18000aec2  mov     rax, rdx
0x18000aec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeca  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000aed1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000aed8  jmp     short loc_18000AEE8
0x18000aeda  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000aee1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000aee8  mov     rcx, [rbx+20h]
0x18000aeec  test    rcx, rcx
0x18000aeef  jz      short loc_18000AF04
0x18000aef1  test    rax, rax
0x18000aef4  jnz     short loc_18000AEFE
0x18000aef6  test    rdx, rdx
0x18000aef9  jz      short loc_18000AF04
0x18000aefb  mov     rax, rdx
0x18000aefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af03  nop
0x18000af04  mov     rbx, [rbx+10h]
0x18000af08  test    rbx, rbx
0x18000af0b  jz      short loc_18000AF48
0x18000af0d  xor     r9d, r9d; msWindowLength
0x18000af10  xor     r8d, r8d; msPeriod
0x18000af13  xor     edx, edx; pftDueTime
0x18000af15  mov     rcx, rbx; pti
0x18000af18  call    cs:__imp_SetThreadpoolTimer
0x18000af1f  nop     dword ptr [rax+rax+00h]
0x18000af24  mov     edx, 1; fCancelPendingCallbacks
0x18000af29  mov     rcx, rbx; pti
0x18000af2c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000af33  nop     dword ptr [rax+rax+00h]
0x18000af38  mov     rcx, rbx; pti
0x18000af3b  call    cs:__imp_CloseThreadpoolTimer
0x18000af42  nop     dword ptr [rax+rax+00h]
0x18000af47  nop
0x18000af48  mov     rbx, [rsp+28h+arg_0]
0x18000af4d  mov     rsi, [rsp+28h+arg_8]
0x18000af52  add     rsp, 20h
0x18000af56  pop     rdi
0x18000af57  retn
```
