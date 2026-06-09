# wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x140007e98`
- end: `0x140007f0e`
- name: `??$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `118`
- prototype: `void __fastcall(_QWORD *, _BYTE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000f00c`

## callees

- `0x1400039f0`
- `0x140003dd0`
- `0x140007e98`
- `0x14000b29c`
- `0x140012c04`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140007ed2`
- `KERNEL32!CreateThreadpoolTimer` at `0x140007ed2`

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
0x140007e98  mov     [rsp+arg_0], rbx
0x140007e9d  mov     [rsp+arg_10], rsi
0x140007ea2  push    rdi
0x140007ea3  sub     rsp, 20h
0x140007ea7  cmp     byte ptr [rdx], 0
0x140007eaa  mov     rsi, r8
0x140007ead  mov     rdi, rdx
0x140007eb0  mov     rbx, rcx
0x140007eb3  jnz     short loc_140007EFE
0x140007eb5  cmp     qword ptr [rcx], 0
0x140007eb9  jnz     short loc_140007EED
0x140007ebb  lea     rcx, [rsp+28h+arg_8]; this
0x140007ec0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140007ec5  xor     r8d, r8d; pcbe
0x140007ec8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007ecf  mov     rdx, rsi; pv
0x140007ed2  call    cs:__imp_CreateThreadpoolTimer
0x140007ed8  mov     rdx, rax
0x140007edb  mov     rcx, rbx
0x140007ede  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140007ee3  lea     rcx, [rsp+28h+arg_8]; this
0x140007ee8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140007eed  mov     r8d, 1388h
0x140007ef3  mov     rdx, rdi
0x140007ef6  mov     rcx, rbx
0x140007ef9  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140007efe  mov     rbx, [rsp+28h+arg_0]
0x140007f03  mov     rsi, [rsp+28h+arg_10]
0x140007f08  add     rsp, 20h
0x140007f0c  pop     rdi
0x140007f0d  retn
```
