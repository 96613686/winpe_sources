# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x180008720`
- end: `0x1800087b3`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014c7c`

## callees

- `0x180008720`
- `0x1800087bc`
- `0x1800087dc`
- `0x180008800`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000875a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000875a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000879a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000879a`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
        struct _TP_TIMER **a1,
        _BYTE *a2,
        void *a3)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v7; // rcx
  _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

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
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x180008720  mov     [rsp+arg_0], rbx
0x180008725  mov     [rsp+arg_10], rsi
0x18000872a  push    rdi
0x18000872b  sub     rsp, 20h
0x18000872f  cmp     byte ptr [rdx], 0
0x180008732  mov     rsi, r8
0x180008735  mov     rdi, rdx
0x180008738  mov     rbx, rcx
0x18000873b  jnz     short loc_1800087A3
0x18000873d  cmp     qword ptr [rcx], 0
0x180008741  jnz     short loc_180008775
0x180008743  lea     rcx, [rsp+28h+pftDueTime]; this
0x180008748  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000874d  xor     r8d, r8d; pcbe
0x180008750  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008757  mov     rdx, rsi; pv
0x18000875a  call    cs:__imp_CreateThreadpoolTimer
0x180008760  mov     rdx, rax
0x180008763  mov     rcx, rbx
0x180008766  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000876b  lea     rcx, [rsp+28h+pftDueTime]; this
0x180008770  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008775  mov     rcx, [rbx]; pti
0x180008778  test    rcx, rcx
0x18000877b  jz      short loc_1800087A3
0x18000877d  mov     rax, 0FFFFFFFF4D2FA200h
0x180008787  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000878c  mov     r9d, 124F8h; msWindowLength
0x180008792  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180008797  xor     r8d, r8d; msPeriod
0x18000879a  call    cs:__imp_SetThreadpoolTimer
0x1800087a0  mov     byte ptr [rdi], 1
0x1800087a3  mov     rbx, [rsp+28h+arg_0]
0x1800087a8  mov     rsi, [rsp+28h+arg_10]
0x1800087ad  add     rsp, 20h
0x1800087b1  pop     rdi
0x1800087b2  retn
```
