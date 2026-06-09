# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x180006c24`
- end: `0x180006cb7`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `147`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ae14`

## callees

- `0x180002f90`
- `0x180003274`
- `0x180005654`
- `0x180006c24`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006c5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006c5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006c9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006c9e`

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
0x180006c24  mov     [rsp+arg_0], rbx
0x180006c29  mov     [rsp+arg_10], rsi
0x180006c2e  push    rdi
0x180006c2f  sub     rsp, 20h
0x180006c33  cmp     byte ptr [rdx], 0
0x180006c36  mov     rsi, r8
0x180006c39  mov     rdi, rdx
0x180006c3c  mov     rbx, rcx
0x180006c3f  jnz     short loc_180006CA7
0x180006c41  cmp     qword ptr [rcx], 0
0x180006c45  jnz     short loc_180006C79
0x180006c47  lea     rcx, [rsp+28h+pftDueTime]; this
0x180006c4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006c51  xor     r8d, r8d; pcbe
0x180006c54  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006c5b  mov     rdx, rsi; pv
0x180006c5e  call    cs:__imp_CreateThreadpoolTimer
0x180006c64  mov     rdx, rax
0x180006c67  mov     rcx, rbx
0x180006c6a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006c6f  lea     rcx, [rsp+28h+pftDueTime]; this
0x180006c74  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006c79  mov     rcx, [rbx]; pti
0x180006c7c  test    rcx, rcx
0x180006c7f  jz      short loc_180006CA7
0x180006c81  mov     rax, 0FFFFFFFF4D2FA200h
0x180006c8b  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180006c90  mov     r9d, 124F8h; msWindowLength
0x180006c96  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180006c9b  xor     r8d, r8d; msPeriod
0x180006c9e  call    cs:__imp_SetThreadpoolTimer
0x180006ca4  mov     byte ptr [rdi], 1
0x180006ca7  mov     rbx, [rsp+28h+arg_0]
0x180006cac  mov     rsi, [rsp+28h+arg_10]
0x180006cb1  add     rsp, 20h
0x180006cb5  pop     rdi
0x180006cb6  retn
```
