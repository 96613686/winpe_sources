# wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x180007334`
- end: `0x1800073aa`
- name: `??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000be04`

## callees

- `0x180006fac`
- `0x180007030`
- `0x180007334`
- `0x18000ac30`
- `0x18000aec0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000736e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000736e`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(_QWORD *a1, _BYTE *a2, void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    wil::details::EnsureCoalescedTimer_SetTimer(a1, a2, 300000);
  }
}

```

## disassembly

```asm
0x180007334  mov     [rsp+arg_0], rbx
0x180007339  mov     [rsp+arg_10], rsi
0x18000733e  push    rdi
0x18000733f  sub     rsp, 20h
0x180007343  cmp     byte ptr [rdx], 0
0x180007346  mov     rsi, r8
0x180007349  mov     rdi, rdx
0x18000734c  mov     rbx, rcx
0x18000734f  jnz     short loc_18000739A
0x180007351  cmp     qword ptr [rcx], 0
0x180007355  jnz     short loc_180007389
0x180007357  lea     rcx, [rsp+28h+arg_8]; this
0x18000735c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007361  xor     r8d, r8d; pcbe
0x180007364  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000736b  mov     rdx, rsi; pv
0x18000736e  call    cs:__imp_CreateThreadpoolTimer
0x180007374  mov     rdx, rax
0x180007377  mov     rcx, rbx
0x18000737a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000737f  lea     rcx, [rsp+28h+arg_8]; this
0x180007384  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007389  mov     r8d, 493E0h
0x18000738f  mov     rdx, rdi
0x180007392  mov     rcx, rbx
0x180007395  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000739a  mov     rbx, [rsp+28h+arg_0]
0x18000739f  mov     rsi, [rsp+28h+arg_10]
0x1800073a4  add     rsp, 20h
0x1800073a8  pop     rdi
0x1800073a9  retn
```
