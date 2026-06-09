# Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_________CRdpIdSwapchain::CRdpIdSwapchain_::_8_::_lambda_1__&_

- ea: `0x180028198`
- end: `0x1800282b9`
- name: `Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_________CRdpIdSwapchain::CRdpIdSwapchain_::_8_::_lambda_1__&_`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002a054`

## callees

- `0x180009004`
- `0x18000c354`
- `0x18000e9b8`
- `0x180028198`
- `0x180028afc`
- `0x18002baa0`
- `0x18002d450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028231`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028222`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028231`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180028266`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180028266`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char *__fastcall Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_________CRdpIdSwapchain::CRdpIdSwapchain_::_8_::_lambda_1____(
        char *pv,
        HANDLE hSourceHandle,
        __int128 *a3,
        __int64 a4)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  __int64 v10; // r8
  const char *v11; // r9
  __int128 v13; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HANDLE TargetHandle; // [rsp+80h] [rbp+18h] BYREF

  *(_QWORD *)pv = &Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::`vftable';
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 0;
  Rdp::Utils::Synchronization::rundown_mutex::rundown_mutex((Rdp::Utils::Synchronization::rundown_mutex *)(pv + 88));
  *((_QWORD *)pv + 23) = 0;
  *((_QWORD *)pv + 24) = 0;
  v13 = *a3;
  Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::InitTimeout(
    pv,
    &v13);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v9 = GetCurrentProcess();
  if ( !DuplicateHandle(v9, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xFD, v10, v11);
  Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__CRdpIdSwapchain::CRdpIdSwapchain_::_8_::_lambda_1____(
    pv,
    (__int64)&TargetHandle,
    a4);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  return pv;
}

```

## disassembly

```asm
0x180028198  mov     [rsp+arg_8], rbx
0x18002819d  mov     [rsp+arg_0], rcx
0x1800281a2  push    rbp
0x1800281a3  push    rsi
0x1800281a4  push    rdi
0x1800281a5  sub     rsp, 50h
0x1800281a9  mov     rbp, r9
0x1800281ac  mov     rbx, r8
0x1800281af  mov     rdi, rdx
0x1800281b2  mov     rsi, rcx
0x1800281b5  lea     rax, ??_7?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@6B@; const Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::`vftable'
0x1800281bc  mov     [rcx], rax
0x1800281bf  mov     qword ptr [rcx+8], 0
0x1800281c7  mov     qword ptr [rcx+48h], 0
0x1800281cf  mov     qword ptr [rcx+50h], 0
0x1800281d7  add     rcx, 58h ; 'X'; this
0x1800281db  call    ??0rundown_mutex@Synchronization@Utils@Rdp@@QEAA@XZ; Rdp::Utils::Synchronization::rundown_mutex::rundown_mutex(void)
0x1800281e0  nop
0x1800281e1  xor     eax, eax
0x1800281e3  mov     [rsi+0B8h], rax
0x1800281ea  mov     [rsi+0C0h], rax
0x1800281f1  movaps  xmm0, xmmword ptr [rbx]
0x1800281f4  movdqa  [rsp+68h+var_28], xmm0
0x1800281fa  lea     rdx, [rsp+68h+var_28]
0x1800281ff  mov     rcx, rsi
0x180028202  call    ?InitTimeout@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@AEAAXV?$optional@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@std@@@Z; Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::InitTimeout(std::optional<std::chrono::duration<__int64,std::ratio<1,1000>>>)
0x180028207  mov     [rsp+68h+TargetHandle], 0
0x180028213  xor     edx, edx
0x180028215  lea     rcx, [rsp+68h+TargetHandle]
0x18002821d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028222  call    cs:__imp_GetCurrentProcess
0x180028229  nop     dword ptr [rax+rax+00h]
0x18002822e  mov     rbx, rax
0x180028231  call    cs:__imp_GetCurrentProcess
0x180028238  nop     dword ptr [rax+rax+00h]
0x18002823d  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180028245  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18002824d  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180028255  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18002825d  mov     r8, rbx; hTargetProcessHandle
0x180028260  mov     rdx, rdi; hSourceHandle
0x180028263  mov     rcx, rax; hSourceProcessHandle
0x180028266  call    cs:__imp_DuplicateHandle
0x18002826d  nop     dword ptr [rax+rax+00h]
0x180028272  mov     rcx, [rsp+68h]; this
0x180028277  test    eax, eax
0x180028279  jz      short loc_1800282AE
0x18002827b  mov     r8, rbp
0x18002827e  lea     rdx, [rsp+68h+TargetHandle]
0x180028286  mov     rcx, rsi; pv
0x180028289  call    Rdp__Utils__TP__details__CThreadPoolWait_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp__Utils__TP__details__DestroyThreadpoolWait_wistd__integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std__nullptr_t_________RegisterWait__CRdpIdSwapchain__CRdpIdSwapchain____8____lambda_1____
0x18002828e  nop
0x18002828f  lea     rcx, [rsp+68h+TargetHandle]
0x180028297  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002829c  nop
0x18002829d  mov     rax, rsi
0x1800282a0  mov     rbx, [rsp+68h+arg_8]
0x1800282a5  add     rsp, 50h
0x1800282a9  pop     rdi
0x1800282aa  pop     rsi
0x1800282ab  pop     rbp
0x1800282ac  retn
0x1800282ae  mov     edx, 0FDh; void *
0x1800282b3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
