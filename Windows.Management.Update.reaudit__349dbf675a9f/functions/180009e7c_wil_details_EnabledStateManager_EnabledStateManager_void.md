# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180009e7c`
- end: `0x180009fbf`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `323`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b0c0`

## callees

- `0x180009e7c`
- `0x18000d214`
- `0x180010774`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009f7e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009f92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009fa1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009fa1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  __int64 v2; // rdx
  void (*v3)(void); // rax
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
    v2 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v3 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_8;
  }
  v2 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v3 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  else
  {
    v3 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_8;
  }
  v3();
  v3 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v2 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_8:
  if ( !this[12] )
    goto LABEL_13;
  if ( v2 )
  {
    v3 = (void (*)(void))v2;
  }
  else if ( !v3 )
  {
    goto LABEL_13;
  }
  v3();
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
0x180009e7c  mov     [rsp+arg_0], rbx
0x180009e81  mov     [rsp+arg_8], rsi
0x180009e86  push    rdi
0x180009e87  sub     rsp, 20h
0x180009e8b  mov     rbx, rcx
0x180009e8e  mov     dword ptr [rcx], 0
0x180009e94  xor     edx, edx
0x180009e96  add     rcx, 10h
0x180009e9a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009e9f  mov     rcx, rbx; this
0x180009ea2  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180009ea7  mov     rcx, [rbx+68h]
0x180009eab  test    rcx, rcx
0x180009eae  jz      short loc_180009EE2
0x180009eb0  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009eb7  test    rdx, rdx
0x180009eba  jz      short loc_180009EC1
0x180009ebc  mov     rax, rdx
0x180009ebf  jmp     short loc_180009ECD
0x180009ec1  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009ec8  test    rax, rax
0x180009ecb  jz      short loc_180009EE0
0x180009ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed2  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009ed9  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009ee0  jmp     short loc_180009EF0
0x180009ee2  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180009ee9  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180009ef0  mov     rcx, [rbx+60h]
0x180009ef4  test    rcx, rcx
0x180009ef7  jz      short loc_180009F0E
0x180009ef9  test    rdx, rdx
0x180009efc  jz      short loc_180009F03
0x180009efe  mov     rax, rdx
0x180009f01  jmp     short loc_180009F08
0x180009f03  test    rax, rax
0x180009f06  jz      short loc_180009F0E
0x180009f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f0d  nop
0x180009f0e  mov     rdi, [rbx+58h]
0x180009f12  and     qword ptr [rbx+58h], 0
0x180009f17  test    rdi, rdi
0x180009f1a  jz      short loc_180009F3C
0x180009f1c  call    cs:__imp_GetProcessHeap
0x180009f23  nop     dword ptr [rax+rax+00h]
0x180009f28  mov     rcx, rax; hHeap
0x180009f2b  mov     r8, rdi; lpMem
0x180009f2e  xor     edx, edx; dwFlags
0x180009f30  call    cs:__imp_HeapFree
0x180009f37  nop     dword ptr [rax+rax+00h]
0x180009f3c  mov     rdi, [rbx+38h]
0x180009f40  and     qword ptr [rbx+38h], 0
0x180009f45  test    rdi, rdi
0x180009f48  jz      short loc_180009F6A
0x180009f4a  call    cs:__imp_GetProcessHeap
0x180009f51  nop     dword ptr [rax+rax+00h]
0x180009f56  mov     rcx, rax; hHeap
0x180009f59  mov     r8, rdi; lpMem
0x180009f5c  xor     edx, edx; dwFlags
0x180009f5e  call    cs:__imp_HeapFree
0x180009f65  nop     dword ptr [rax+rax+00h]
0x180009f6a  mov     rbx, [rbx+10h]
0x180009f6e  test    rbx, rbx
0x180009f71  jz      short loc_180009FAE
0x180009f73  xor     r9d, r9d; msWindowLength
0x180009f76  xor     r8d, r8d; msPeriod
0x180009f79  xor     edx, edx; pftDueTime
0x180009f7b  mov     rcx, rbx; pti
0x180009f7e  call    cs:__imp_SetThreadpoolTimer
0x180009f85  nop     dword ptr [rax+rax+00h]
0x180009f8a  mov     edx, 1; fCancelPendingCallbacks
0x180009f8f  mov     rcx, rbx; pti
0x180009f92  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009f99  nop     dword ptr [rax+rax+00h]
0x180009f9e  mov     rcx, rbx; pti
0x180009fa1  call    cs:__imp_CloseThreadpoolTimer
0x180009fa8  nop     dword ptr [rax+rax+00h]
0x180009fad  nop
0x180009fae  mov     rbx, [rsp+28h+arg_0]
0x180009fb3  mov     rsi, [rsp+28h+arg_8]
0x180009fb8  add     rsp, 20h
0x180009fbc  pop     rdi
0x180009fbd  retn
```
