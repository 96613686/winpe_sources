# wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)

- ea: `0x18004bb7c`
- end: `0x18004bc1c`
- name: `??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005bd50`

## callees

- `0x18004bb7c`
- `0x18004bc24`
- `0x18004bc4c`
- `0x18004bc78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004bbfc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004bbfc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004bbb6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004bbb6`

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
0x18004bb7c  mov     [rsp+arg_0], rbx
0x18004bb81  mov     [rsp+arg_10], rsi
0x18004bb86  push    rdi
0x18004bb87  sub     rsp, 20h
0x18004bb8b  cmp     byte ptr [rdx], 0
0x18004bb8e  mov     rsi, r8
0x18004bb91  mov     rdi, rdx
0x18004bb94  mov     rbx, rcx
0x18004bb97  jnz     short loc_18004BC0B
0x18004bb99  cmp     qword ptr [rcx], 0
0x18004bb9d  jnz     short loc_18004BBD7
0x18004bb9f  lea     rcx, [rsp+28h+pftDueTime]; this
0x18004bba4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004bba9  xor     r8d, r8d; pcbe
0x18004bbac  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004bbb3  mov     rdx, rsi; pv
0x18004bbb6  call    cs:__imp_CreateThreadpoolTimer
0x18004bbbd  nop     dword ptr [rax+rax+00h]
0x18004bbc2  mov     rdx, rax
0x18004bbc5  mov     rcx, rbx
0x18004bbc8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004bbcd  lea     rcx, [rsp+28h+pftDueTime]; this
0x18004bbd2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004bbd7  mov     rcx, [rbx]; pti
0x18004bbda  test    rcx, rcx
0x18004bbdd  jz      short loc_18004BC0B
0x18004bbdf  mov     rax, 0FFFFFFFF4D2FA200h
0x18004bbe9  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18004bbee  mov     r9d, 124F8h; msWindowLength
0x18004bbf4  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18004bbf9  xor     r8d, r8d; msPeriod
0x18004bbfc  call    cs:__imp_SetThreadpoolTimer
0x18004bc03  nop     dword ptr [rax+rax+00h]
0x18004bc08  mov     byte ptr [rdi], 1
0x18004bc0b  mov     rbx, [rsp+28h+arg_0]
0x18004bc10  mov     rsi, [rsp+28h+arg_10]
0x18004bc15  add     rsp, 20h
0x18004bc19  pop     rdi
0x18004bc1a  retn
```
