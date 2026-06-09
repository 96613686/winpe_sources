# wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x1800080fc`
- end: `0x180008172`
- name: `??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `118`
- prototype: `void __fastcall(_QWORD *, _BYTE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ad28`

## callees

- `0x1800054e0`
- `0x180005790`
- `0x1800080fc`
- `0x1800090f0`
- `0x18000c424`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008136`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008136`

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
0x1800080fc  mov     [rsp+arg_0], rbx
0x180008101  mov     [rsp+arg_10], rsi
0x180008106  push    rdi
0x180008107  sub     rsp, 20h
0x18000810b  cmp     byte ptr [rdx], 0
0x18000810e  mov     rsi, r8
0x180008111  mov     rdi, rdx
0x180008114  mov     rbx, rcx
0x180008117  jnz     short loc_180008162
0x180008119  cmp     qword ptr [rcx], 0
0x18000811d  jnz     short loc_180008151
0x18000811f  lea     rcx, [rsp+28h+arg_8]; this
0x180008124  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008129  xor     r8d, r8d; pcbe
0x18000812c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008133  mov     rdx, rsi; pv
0x180008136  call    cs:__imp_CreateThreadpoolTimer
0x18000813c  mov     rdx, rax
0x18000813f  mov     rcx, rbx
0x180008142  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008147  lea     rcx, [rsp+28h+arg_8]; this
0x18000814c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008151  mov     r8d, 493E0h
0x180008157  mov     rdx, rdi
0x18000815a  mov     rcx, rbx
0x18000815d  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180008162  mov     rbx, [rsp+28h+arg_0]
0x180008167  mov     rsi, [rsp+28h+arg_10]
0x18000816c  add     rsp, 20h
0x180008170  pop     rdi
0x180008171  retn
```
