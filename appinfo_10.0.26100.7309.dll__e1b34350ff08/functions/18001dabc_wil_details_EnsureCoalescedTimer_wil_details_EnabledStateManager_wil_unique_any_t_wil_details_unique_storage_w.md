# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x18001dabc`
- end: `0x18001db39`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180019668`

## callees

- `0x180010f70`
- `0x1800121a4`
- `0x180019f80`
- `0x18001dabc`
- `0x18001edb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001daf6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001daf6`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(_QWORD *a1, _BYTE *a2, void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, a3, 0);
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
0x18001dabc  mov     [rsp+arg_0], rbx
0x18001dac1  mov     [rsp+arg_10], rsi
0x18001dac6  push    rdi
0x18001dac7  sub     rsp, 20h
0x18001dacb  cmp     byte ptr [rdx], 0
0x18001dace  mov     rsi, r8
0x18001dad1  mov     rdi, rdx
0x18001dad4  mov     rbx, rcx
0x18001dad7  jnz     short loc_18001DB28
0x18001dad9  cmp     qword ptr [rcx], 0
0x18001dadd  jnz     short loc_18001DB17
0x18001dadf  lea     rcx, [rsp+28h+arg_8]; this
0x18001dae4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001dae9  xor     r8d, r8d; pcbe
0x18001daec  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001daf3  mov     rdx, rsi; pv
0x18001daf6  call    cs:__imp_CreateThreadpoolTimer
0x18001dafd  nop     dword ptr [rax+rax+00h]
0x18001db02  mov     rdx, rax
0x18001db05  mov     rcx, rbx
0x18001db08  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001db0d  lea     rcx, [rsp+28h+arg_8]; this
0x18001db12  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001db17  mov     r8d, 493E0h
0x18001db1d  mov     rdx, rdi
0x18001db20  mov     rcx, rbx
0x18001db23  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001db28  mov     rbx, [rsp+28h+arg_0]
0x18001db2d  mov     rsi, [rsp+28h+arg_10]
0x18001db32  add     rsp, 20h
0x18001db36  pop     rdi
0x18001db37  retn
```
