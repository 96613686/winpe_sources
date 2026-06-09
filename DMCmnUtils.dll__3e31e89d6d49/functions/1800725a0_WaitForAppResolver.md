# WaitForAppResolver

- ea: `0x1800725a0`
- end: `0x1800726cf`
- name: `WaitForAppResolver`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18006fc44`

## callees

- `0x180007270`
- `0x180053e88`
- `0x180053f9c`
- `0x180057c6c`
- `0x18005958c`
- `0x18005bcd8`
- `0x18006f3bc`
- `0x18006f614`
- `0x18006f8ec`
- `0x1800719a4`
- `0x1800725a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007263a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007263a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007264e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007264e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WaitForAppResolver()
{
  int v0; // eax
  unsigned int v1; // ebx
  void *v3; // rdx
  HANDLE Event; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // r8d
  int v9; // r9d
  int v10; // [rsp+20h] [rbp-49h] BYREF
  int v11; // [rsp+24h] [rbp-45h] BYREF
  unsigned int v12; // [rsp+28h] [rbp-41h] BYREF
  wil *v13; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v15[14]; // [rsp+40h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v12 = 0;
  v11 = 0;
  v0 = wil::wnf_query_nothrow<unsigned long>(&WNF_SHEL_APPRESOLVER_SCAN, &v10, &v11, &v12);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v13 = 0;
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::FailFast_GetLastError(retaddr, v3, v5, v6);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v13,
      Event);
    v15[0] = off_1800C3FF8;
    v15[1] = &v13;
    v15[13] = v15;
    wil::make_wnf_subscription<unsigned long>(&v12, v7, v14, v12);
    wistd::function<void (unsigned long const &)>::~function<void (unsigned long const &)>(v14);
    wil::handle_wait(v13, (void *)0xFA0, v8, v9);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v12);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)(unsigned int)v0,
      v10);
    return v1;
  }
}

```

## disassembly

```asm
0x1800725a0  mov     [rsp-8+arg_0], rbx
0x1800725a5  push    rbp
0x1800725a6  lea     rbp, [rsp-57h]
0x1800725ab  sub     rsp, 0C0h
0x1800725b2  mov     rax, cs:__security_cookie
0x1800725b9  xor     rax, rsp
0x1800725bc  mov     [rbp+57h+var_10], rax
0x1800725c0  mov     [rbp+57h+var_98], 0
0x1800725c7  mov     [rbp+57h+var_9C], 0
0x1800725ce  lea     r9, [rbp+57h+var_98]
0x1800725d2  lea     r8, [rbp+57h+var_9C]
0x1800725d6  lea     rdx, [rbp+57h+var_A0]
0x1800725da  lea     rcx, WNF_SHEL_APPRESOLVER_SCAN
0x1800725e1  call    ??$wnf_query_nothrow@K@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAKPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<ulong>(_WNF_STATE_NAME const &,bool *,ulong *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800725e6  mov     ebx, eax
0x1800725e8  test    eax, eax
0x1800725ea  jns     short loc_180072624
0x1800725ec  mov     rcx, [rbp+5Fh]; this
0x1800725f0  mov     r9d, eax; char *
0x1800725f3  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x1800725fa  mov     edx, 48h ; 'H'; void *
0x1800725ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072604  mov     eax, ebx
0x180072606  mov     rcx, [rbp+57h+var_10]
0x18007260a  xor     rcx, rsp; StackCookie
0x18007260d  call    __security_check_cookie
0x180072612  mov     rbx, [rsp+0C0h+arg_0]
0x18007261a  add     rsp, 0C0h
0x180072621  pop     rbp
0x180072622  retn
0x180072624  mov     [rbp+57h+var_90], 0
0x18007262c  xor     edx, edx; lpName
0x18007262e  xor     ecx, ecx; lpEventAttributes
0x180072630  mov     r9d, 1F0003h; dwDesiredAccess
0x180072636  lea     r8d, [rdx+1]; dwFlags
0x18007263a  call    cs:__imp_CreateEventExW
0x180072641  nop     dword ptr [rax+rax+00h]
0x180072646  mov     rbx, rax
0x180072649  test    rax, rax
0x18007264c  jz      short loc_1800726C5
0x18007264e  call    cs:__imp_GetLastError
0x180072655  nop     dword ptr [rax+rax+00h]
0x18007265a  mov     rdx, rbx
0x18007265d  lea     rcx, [rbp+57h+var_90]
0x180072661  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180072666  nop
0x180072667  lea     rax, off_1800C3FF8
0x18007266e  mov     [rbp+57h+var_80], rax
0x180072672  lea     rax, [rbp+57h+var_90]
0x180072676  mov     [rbp+57h+var_78], rax
0x18007267a  lea     rax, [rbp+57h+var_80]
0x18007267e  mov     [rbp+57h+var_18], rax
0x180072682  mov     r9d, [rbp+57h+var_98]
0x180072686  lea     r8, [rbp+57h+var_88]
0x18007268a  lea     rcx, [rbp+57h+var_98]
0x18007268e  call    ??$make_wnf_subscription@K@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBK@Z@wistd@@K@Z; wil::make_wnf_subscription<ulong>(_WNF_STATE_NAME const &,wistd::function<void (ulong const &)> &&,ulong)
0x180072693  nop
0x180072694  lea     rcx, [rbp+57h+var_88]
0x180072698  call    ??1?$function@$$A6AXAEBK@Z@wistd@@QEAA@XZ; wistd::function<void (ulong const &)>::~function<void (ulong const &)>(void)
0x18007269d  mov     edx, 0FA0h; void *
0x1800726a2  mov     rcx, [rbp+57h+var_90]; this
0x1800726a6  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800726ab  lea     rcx, [rbp+57h+var_98]
0x1800726af  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800726b4  nop
0x1800726b5  lea     rcx, [rbp+57h+var_90]
0x1800726b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800726be  xor     eax, eax
0x1800726c0  jmp     loc_180072606
0x1800726c5  mov     rcx, [rbp+5Fh]; this
0x1800726c9  call    ?FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_GetLastError(void *,uint,char const *)
```
