# wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x140008ec8`
- end: `0x140008f45`
- name: `??$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000ccd4`

## callees

- `0x1400048c8`
- `0x140004d00`
- `0x140008ec8`
- `0x14000b840`
- `0x140011dd4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008f02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008f02`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(
        _QWORD *a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    wil::details::EnsureCoalescedTimer_SetTimer(a1, a2, 5000);
  }
}

```

## disassembly

```asm
0x140008ec8  mov     [rsp+arg_0], rbx
0x140008ecd  mov     [rsp+arg_10], rsi
0x140008ed2  push    rdi
0x140008ed3  sub     rsp, 20h
0x140008ed7  cmp     byte ptr [rdx], 0
0x140008eda  mov     rsi, r8
0x140008edd  mov     rdi, rdx
0x140008ee0  mov     rbx, rcx
0x140008ee3  jnz     short loc_140008F34
0x140008ee5  cmp     qword ptr [rcx], 0
0x140008ee9  jnz     short loc_140008F23
0x140008eeb  lea     rcx, [rsp+28h+arg_8]; this
0x140008ef0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140008ef5  xor     r8d, r8d; pcbe
0x140008ef8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008eff  mov     rdx, rsi; pv
0x140008f02  call    cs:__imp_CreateThreadpoolTimer
0x140008f09  nop     dword ptr [rax+rax+00h]
0x140008f0e  mov     rdx, rax
0x140008f11  mov     rcx, rbx
0x140008f14  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140008f19  lea     rcx, [rsp+28h+arg_8]; this
0x140008f1e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140008f23  mov     r8d, 1388h
0x140008f29  mov     rdx, rdi
0x140008f2c  mov     rcx, rbx
0x140008f2f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140008f34  mov     rbx, [rsp+28h+arg_0]
0x140008f39  mov     rsi, [rsp+28h+arg_10]
0x140008f3e  add     rsp, 20h
0x140008f42  pop     rdi
0x140008f43  retn
```
