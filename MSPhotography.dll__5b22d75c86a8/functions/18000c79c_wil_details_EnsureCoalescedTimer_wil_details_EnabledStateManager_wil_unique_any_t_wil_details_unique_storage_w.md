# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x18000c79c`
- end: `0x18000c82f`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017284`

## callees

- `0x180004460`
- `0x1800046c4`
- `0x18000c79c`
- `0x18001d3d8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c816`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c816`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c7d6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c7d6`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a2 )
  {
    if ( !*a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&pftDueTime);
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, a3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        a1,
        ThreadpoolTimer);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pftDueTime);
    }
    v7 = *a1;
    if ( *a1 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x18000c79c  mov     [rsp+arg_0], rbx
0x18000c7a1  mov     [rsp+arg_10], rsi
0x18000c7a6  push    rdi
0x18000c7a7  sub     rsp, 20h
0x18000c7ab  cmp     byte ptr [rdx], 0
0x18000c7ae  mov     rsi, r8
0x18000c7b1  mov     rdi, rdx
0x18000c7b4  mov     rbx, rcx
0x18000c7b7  jnz     short loc_18000C81F
0x18000c7b9  cmp     qword ptr [rcx], 0
0x18000c7bd  jnz     short loc_18000C7F1
0x18000c7bf  lea     rcx, [rsp+28h+pftDueTime]; this
0x18000c7c4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c7c9  xor     r8d, r8d; pcbe
0x18000c7cc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c7d3  mov     rdx, rsi; pv
0x18000c7d6  call    cs:__imp_CreateThreadpoolTimer
0x18000c7dc  mov     rdx, rax
0x18000c7df  mov     rcx, rbx
0x18000c7e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000c7e7  lea     rcx, [rsp+28h+pftDueTime]; this
0x18000c7ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c7f1  mov     rcx, [rbx]; pti
0x18000c7f4  test    rcx, rcx
0x18000c7f7  jz      short loc_18000C81F
0x18000c7f9  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c803  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000c808  mov     r9d, 124F8h; msWindowLength
0x18000c80e  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000c813  xor     r8d, r8d; msPeriod
0x18000c816  call    cs:__imp_SetThreadpoolTimer
0x18000c81c  mov     byte ptr [rdi], 1
0x18000c81f  mov     rbx, [rsp+28h+arg_0]
0x18000c824  mov     rsi, [rsp+28h+arg_10]
0x18000c829  add     rsp, 20h
0x18000c82d  pop     rdi
0x18000c82e  retn
```
