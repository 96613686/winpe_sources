# Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2__&_

- ea: `0x180028bac`
- end: `0x180028c55`
- name: `Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2__&_`
- size: `169`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800282c0`

## callees

- `0x18002848c`
- `0x180028bac`
- `0x18002a4e4`
- `0x18002a544`
- `0x18002a580`
- `0x18002d450`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028c29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028c29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180028bcf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180028bcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2____(
        char *pv,
        __int64 a2,
        __int64 a3,
        ...)
{
  unsigned int v6; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PTP_WAIT ThreadpoolWait; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  ThreadpoolWait = va_arg(va1, PTP_WAIT);
  ThreadpoolWait = CreateThreadpoolWait(
                     Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::OnWaitCallback,
                     pv,
                     0);
  if ( !ThreadpoolWait )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x14A, v6, 0);
  std::function_bool___cdecl_unsigned_long__::operator___CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2____0_(
    pv + 16,
    a3);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::operator=(
    pv + 8,
    (PTP_WAIT *)va);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    pv + 80,
    a2);
  SetThreadpoolWait(*((PTP_WAIT *)pv + 1), *((HANDLE *)pv + 10), *((PFILETIME *)pv + 24));
  return wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>((PTP_WAIT *)va);
}

```

## disassembly

```asm
0x180028bac  mov     [rsp+arg_18], r9
0x180028bb1  push    rbx
0x180028bb2  push    rbp
0x180028bb3  push    rsi
0x180028bb4  push    rdi
0x180028bb5  sub     rsp, 28h
0x180028bb9  mov     rbx, r8
0x180028bbc  mov     rbp, rdx
0x180028bbf  mov     rsi, rcx
0x180028bc2  xor     r8d, r8d; pcbe
0x180028bc5  mov     rdx, rcx; pv
0x180028bc8  lea     rcx, ?OnWaitCallback@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180028bcf  call    cs:__imp_CreateThreadpoolWait
0x180028bd6  nop     dword ptr [rax+rax+00h]
0x180028bdb  mov     [rsp+48h+arg_18], rax
0x180028be0  xor     r9d, r9d
0x180028be3  test    rax, rax
0x180028be6  setnz   r9b; char *
0x180028bea  mov     rcx, [rsp+48h]; this
0x180028bef  test    r9d, r9d
0x180028bf2  jz      short loc_180028C4A
0x180028bf4  lea     rcx, [rsi+10h]
0x180028bf8  mov     rdx, rbx
0x180028bfb  call    std__function_bool___cdecl_unsigned_long____operator___CRdpIdSwapchain__CRdpIdSwapchain____15____lambda_2____0_
0x180028c00  lea     rdx, [rsp+48h+arg_18]
0x180028c05  lea     rcx, [rsi+8]
0x180028c09  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> &&)
0x180028c0e  mov     rdx, rbp
0x180028c11  lea     rcx, [rsi+50h]
0x180028c15  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x180028c1a  mov     r8, [rsi+0C0h]; pftTimeout
0x180028c21  mov     rdx, [rsi+50h]; h
0x180028c25  mov     rcx, [rsi+8]; pwa
0x180028c29  call    cs:__imp_SetThreadpoolWait
0x180028c30  nop     dword ptr [rax+rax+00h]
0x180028c35  nop
0x180028c36  lea     rcx, [rsp+48h+arg_18]
0x180028c3b  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x180028c40  add     rsp, 28h
0x180028c44  pop     rdi
0x180028c45  pop     rsi
0x180028c46  pop     rbp
0x180028c47  pop     rbx
0x180028c48  retn
0x180028c4a  mov     edx, 14Ah; void *
0x180028c4f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
