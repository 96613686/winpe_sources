# Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_________CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2__&_

- ea: `0x1800282c0`
- end: `0x1800283e1`
- name: `Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_________CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2__&_`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180029920`

## callees

- `0x180009004`
- `0x18000c354`
- `0x18000e9b8`
- `0x1800282c0`
- `0x180028bac`
- `0x18002baa0`
- `0x18002d450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002834a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028359`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002834a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028359`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002838e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002838e`

## pseudocode

```c
char *__fastcall Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_________CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2____(
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
  Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__CRdpIdSwapchain::CRdpIdSwapchain_::_15_::_lambda_2____(
    pv,
    (__int64)&TargetHandle,
    a4);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  return pv;
}

```

## disassembly

```asm
0x1800282c0  mov     [rsp+arg_8], rbx
0x1800282c5  mov     [rsp+arg_0], rcx
0x1800282ca  push    rbp
0x1800282cb  push    rsi
0x1800282cc  push    rdi
0x1800282cd  sub     rsp, 50h
0x1800282d1  mov     rbp, r9
0x1800282d4  mov     rbx, r8
0x1800282d7  mov     rdi, rdx
0x1800282da  mov     rsi, rcx
0x1800282dd  lea     rax, ??_7?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@6B@; const Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::`vftable'
0x1800282e4  mov     [rcx], rax
0x1800282e7  mov     qword ptr [rcx+8], 0
0x1800282ef  mov     qword ptr [rcx+48h], 0
0x1800282f7  mov     qword ptr [rcx+50h], 0
0x1800282ff  add     rcx, 58h ; 'X'; this
0x180028303  call    ??0rundown_mutex@Synchronization@Utils@Rdp@@QEAA@XZ; Rdp::Utils::Synchronization::rundown_mutex::rundown_mutex(void)
0x180028308  nop
0x180028309  xor     eax, eax
0x18002830b  mov     [rsi+0B8h], rax
0x180028312  mov     [rsi+0C0h], rax
0x180028319  movaps  xmm0, xmmword ptr [rbx]
0x18002831c  movdqa  [rsp+68h+var_28], xmm0
0x180028322  lea     rdx, [rsp+68h+var_28]
0x180028327  mov     rcx, rsi
0x18002832a  call    ?InitTimeout@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@AEAAXV?$optional@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@std@@@Z; Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::InitTimeout(std::optional<std::chrono::duration<__int64,std::ratio<1,1000>>>)
0x18002832f  mov     [rsp+68h+TargetHandle], 0
0x18002833b  xor     edx, edx
0x18002833d  lea     rcx, [rsp+68h+TargetHandle]
0x180028345  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002834a  call    cs:__imp_GetCurrentProcess
0x180028351  nop     dword ptr [rax+rax+00h]
0x180028356  mov     rbx, rax
0x180028359  call    cs:__imp_GetCurrentProcess
0x180028360  nop     dword ptr [rax+rax+00h]
0x180028365  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18002836d  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180028375  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18002837d  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180028385  mov     r8, rbx; hTargetProcessHandle
0x180028388  mov     rdx, rdi; hSourceHandle
0x18002838b  mov     rcx, rax; hSourceProcessHandle
0x18002838e  call    cs:__imp_DuplicateHandle
0x180028395  nop     dword ptr [rax+rax+00h]
0x18002839a  mov     rcx, [rsp+68h]; this
0x18002839f  test    eax, eax
0x1800283a1  jz      short loc_1800283D6
0x1800283a3  mov     r8, rbp
0x1800283a6  lea     rdx, [rsp+68h+TargetHandle]
0x1800283ae  mov     rcx, rsi; pv
0x1800283b1  call    Rdp__Utils__TP__details__CThreadPoolWait_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp__Utils__TP__details__DestroyThreadpoolWait_wistd__integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std__nullptr_t_________RegisterWait__CRdpIdSwapchain__CRdpIdSwapchain____15____lambda_2____
0x1800283b6  nop
0x1800283b7  lea     rcx, [rsp+68h+TargetHandle]
0x1800283bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800283c4  nop
0x1800283c5  mov     rax, rsi
0x1800283c8  mov     rbx, [rsp+68h+arg_8]
0x1800283cd  add     rsp, 50h
0x1800283d1  pop     rdi
0x1800283d2  pop     rsi
0x1800283d3  pop     rbp
0x1800283d4  retn
0x1800283d6  mov     edx, 0FDh; void *
0x1800283db  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
