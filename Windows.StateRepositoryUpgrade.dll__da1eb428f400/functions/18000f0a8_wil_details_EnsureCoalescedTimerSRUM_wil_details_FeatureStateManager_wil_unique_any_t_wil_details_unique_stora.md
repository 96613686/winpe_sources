# wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)

- ea: `0x18000f0a8`
- end: `0x18000f11e`
- name: `??$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010748`

## callees

- `0x180008afc`
- `0x180008d6c`
- `0x18000f0a8`
- `0x18000fa10`
- `0x18001238c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f0e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f0e2`

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
0x18000f0a8  mov     [rsp+arg_0], rbx
0x18000f0ad  mov     [rsp+arg_10], rsi
0x18000f0b2  push    rdi
0x18000f0b3  sub     rsp, 20h
0x18000f0b7  cmp     byte ptr [rdx], 0
0x18000f0ba  mov     rsi, r8
0x18000f0bd  mov     rdi, rdx
0x18000f0c0  mov     rbx, rcx
0x18000f0c3  jnz     short loc_18000F10E
0x18000f0c5  cmp     qword ptr [rcx], 0
0x18000f0c9  jnz     short loc_18000F0FD
0x18000f0cb  lea     rcx, [rsp+28h+arg_8]; this
0x18000f0d0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000f0d5  xor     r8d, r8d; pcbe
0x18000f0d8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f0df  mov     rdx, rsi; pv
0x18000f0e2  call    cs:__imp_CreateThreadpoolTimer
0x18000f0e8  mov     rdx, rax
0x18000f0eb  mov     rcx, rbx
0x18000f0ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f0f3  lea     rcx, [rsp+28h+arg_8]; this
0x18000f0f8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000f0fd  mov     r8d, 1388h
0x18000f103  mov     rdx, rdi
0x18000f106  mov     rcx, rbx
0x18000f109  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000f10e  mov     rbx, [rsp+28h+arg_0]
0x18000f113  mov     rsi, [rsp+28h+arg_10]
0x18000f118  add     rsp, 20h
0x18000f11c  pop     rdi
0x18000f11d  retn
```
