# ThreadManager::BlockUntilSafeToUninitializeXaml(void)

- ea: `0x18000f52c`
- end: `0x18000f738`
- name: `?BlockUntilSafeToUninitializeXaml@ThreadManager@@AEAAXXZ`
- size: `524`
- prototype: `void __fastcall(ThreadManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x180016660`

## callees

- `0x180002b20`
- `0x180006818`
- `0x1800090ac`
- `0x18000d0f0`
- `0x18000dd6c`
- `0x18000e2a0`
- `0x18000f52c`
- `0x18001047c`
- `0x18001049c`
- `0x18001475c`
- `0x180016bac`
- `0x180016e34`
- `0x180016e60`
- `0x180016e8c`
- `0x180017a90`
- `0x18001a71c`
- `0x1800450ac`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18000f58b`
- `USER32!GetSystemMetrics` at `0x18000f58b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f571`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f571`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f6af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f6af`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f607`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f619`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f642`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f642`

## string_xrefs

- `0x18000f726`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\resource.h`
- `0x18000f706`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ThreadManager::BlockUntilSafeToUninitializeXaml(RTL_SRWLOCK *this)
{
  int SystemMetrics; // eax
  _QWORD *Ptr; // rdi
  _QWORD *i; // rbx
  _QWORD *v5; // rdi
  _QWORD *j; // rbx
  void *v7; // rdx
  HANDLE Event; // rbx
  unsigned int v9; // r8d
  const char *v10; // r9
  _QWORD *v11; // rbx
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  void *v14; // rcx
  DWORD v15; // eax
  const char *v16; // r9
  unsigned int v17; // eax
  int v18; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v19; // [rsp+28h] [rbp-30h]
  __int128 v20; // [rsp+30h] [rbp-28h] BYREF
  RTL_SRWLOCK *v21; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_1800736F0);
  if ( byte_180073711 )
  {
    v20 = 0;
    AcquireSRWLockExclusive(this + 2);
    v21 = this + 2;
    if ( !this[14].Ptr
      || (SystemMetrics = GetSystemMetrics(0x2000), BYTE4(this[13].Ptr) = SystemMetrics != 0, SystemMetrics) )
    {
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
    }
    else
    {
      Ptr = this[3].Ptr;
      for ( i = (_QWORD *)*Ptr; i != Ptr; i = (_QWORD *)*i )
      {
        if ( UXFrame::IsUsingXaml(*(UXFrame **)(i[2] + 16LL)) )
          goto LABEL_20;
      }
      v5 = this[5].Ptr;
      for ( j = (_QWORD *)*v5; j != v5; j = (_QWORD *)*j )
      {
        if ( UXFrame::IsUsingXaml(*(UXFrame **)(j[2] + 16LL)) )
          goto LABEL_20;
      }
      UXFrameTelemetry::XamlThreadShutdown_WaitingForOtherXamlThread_Start();
      ThreadManager::RefillIdleThreadPool(this);
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( !Event )
        wil::details::in1diag3::Throw_GetLastError(retaddr, v7, v9, v10);
      GetLastError();
      _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
        &v20,
        Event);
      if ( this[12].Ptr == (PVOID)0x7FFFFFFFFFFFFFFLL )
        std::_Xlength_error("list too long");
      v11 = this[11].Ptr;
      ____0AEBV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil______List_node_emplace_op2_V__allocator_U___List_node_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAX_std___std___std__QEAA_AEAV__allocator_U___List_node_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAX_std___1_AEBV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(
        &v18,
        &this[11],
        &v20);
      ++this[12].Ptr;
      v12 = (_QWORD *)v11[1];
      *v19 = v11;
      v19[1] = v12;
      v13 = v19;
      v19 = 0;
      v11[1] = v13;
      *v12 = v13;
      __1___List_node_emplace_op2_V__allocator_U___List_node_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__PEAX_std___std___std__QEAA_XZ(&v18);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
      v14 = (void *)v20;
      if ( (_QWORD)v20 )
        v14 = *(void **)v20;
      v15 = WaitForSingleObjectEx(v14, 0xEA60u, 0);
      if ( v15 == 258 )
      {
        UXFrameTelemetry::XamlThreadShutdown_WaitingForOtherXamlThread_Timeout();
        v17 = wil::verify_hresult<long>(2147943568LL);
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
          (const char *)v17,
          v18);
      }
      if ( v15 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\resource.h",
          v16);
      UXFrameTelemetry::XamlThreadShutdown_WaitingForOtherXamlThread_Stop();
    }
    std::shared_ptr<WindowingBehavior>::~shared_ptr<WindowingBehavior>(&v20);
  }
}

```

## disassembly

```asm
0x18000f52c  push    rbp
0x18000f52e  push    rbx
0x18000f52f  push    rsi
0x18000f530  push    rdi
0x18000f531  mov     rbp, rsp
0x18000f534  sub     rsp, 58h
0x18000f538  mov     rax, cs:__security_cookie
0x18000f53f  xor     rax, rsp
0x18000f542  mov     [rbp+var_10], rax
0x18000f546  mov     rsi, rcx
0x18000f549  lea     rcx, unk_1800736F0; this
0x18000f550  call    ?ensure_initialized@config_property_base@fc@@IEAAXXZ; fc::config_property_base::ensure_initialized(void)
0x18000f555  cmp     cs:byte_180073711, 0
0x18000f55c  jz      loc_18000F6DA
0x18000f562  xorps   xmm1, xmm1
0x18000f565  movdqu  [rbp+var_28], xmm1
0x18000f56a  lea     rbx, [rsi+10h]
0x18000f56e  mov     rcx, rbx; SRWLock
0x18000f571  call    cs:__imp_AcquireSRWLockExclusive
0x18000f577  mov     [rbp+var_18], rbx
0x18000f57b  cmp     qword ptr [rsi+70h], 0
0x18000f580  jz      loc_18000F6C7
0x18000f586  mov     ecx, 2000h; nIndex
0x18000f58b  call    cs:__imp_GetSystemMetrics
0x18000f591  test    eax, eax
0x18000f593  setnz   cl
0x18000f596  mov     [rsi+6Ch], cl
0x18000f599  test    eax, eax
0x18000f59b  jnz     loc_18000F6C7
0x18000f5a1  mov     rdi, [rsi+18h]
0x18000f5a5  mov     rbx, [rdi]
0x18000f5a8  cmp     rbx, rdi
0x18000f5ab  jz      short loc_18000F5C7
0x18000f5ad  mov     rcx, [rbx+10h]
0x18000f5b1  mov     rcx, [rcx+10h]; this
0x18000f5b5  call    ?IsUsingXaml@UXFrame@@QEBA_NXZ; UXFrame::IsUsingXaml(void)
0x18000f5ba  test    al, al
0x18000f5bc  jnz     loc_18000F6C7
0x18000f5c2  mov     rbx, [rbx]
0x18000f5c5  jmp     short loc_18000F5A8
0x18000f5c7  mov     rdi, [rsi+28h]
0x18000f5cb  mov     rbx, [rdi]
0x18000f5ce  cmp     rbx, rdi
0x18000f5d1  jz      short loc_18000F5ED
0x18000f5d3  mov     rcx, [rbx+10h]
0x18000f5d7  mov     rcx, [rcx+10h]; this
0x18000f5db  call    ?IsUsingXaml@UXFrame@@QEBA_NXZ; UXFrame::IsUsingXaml(void)
0x18000f5e0  test    al, al
0x18000f5e2  jnz     loc_18000F6C7
0x18000f5e8  mov     rbx, [rbx]
0x18000f5eb  jmp     short loc_18000F5CE
0x18000f5ed  call    ?XamlThreadShutdown_WaitingForOtherXamlThread_Start@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::XamlThreadShutdown_WaitingForOtherXamlThread_Start(void)
0x18000f5f2  mov     rcx, rsi
0x18000f5f5  call    ?RefillIdleThreadPool@ThreadManager@@AEAAXUwrite_lock_required@wil@@@Z; ThreadManager::RefillIdleThreadPool(wil::write_lock_required)
0x18000f5fa  mov     r9d, 1F0003h; dwDesiredAccess
0x18000f600  xor     r8d, r8d; dwFlags
0x18000f603  xor     edx, edx; lpName
0x18000f605  xor     ecx, ecx; lpEventAttributes
0x18000f607  call    cs:__imp_CreateEventExW
0x18000f60d  mov     rbx, rax
0x18000f610  test    rax, rax
0x18000f613  jz      loc_18000F718
0x18000f619  call    cs:__imp_GetLastError
0x18000f61f  mov     rdx, rbx
0x18000f622  lea     rcx, [rbp+var_28]
0x18000f626  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f62b  mov     rax, 7FFFFFFFFFFFFFFh
0x18000f635  cmp     [rsi+60h], rax
0x18000f639  jnz     short loc_18000F649
0x18000f63b  lea     rcx, aListTooLong; "list too long"
0x18000f642  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f649  mov     rbx, [rsi+58h]
0x18000f64d  lea     r8, [rbp+var_28]
0x18000f651  lea     rdx, [rsi+58h]
0x18000f655  lea     rcx, [rbp+var_38]
0x18000f659  call    ??$?0AEBV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@std@@@1@AEBV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x18000f65e  inc     qword ptr [rsi+60h]
0x18000f662  mov     rcx, [rbx+8]
0x18000f666  mov     rax, [rbp+var_30]
0x18000f66a  mov     [rax], rbx
0x18000f66d  mov     rax, [rbp+var_30]
0x18000f671  mov     [rax+8], rcx
0x18000f675  mov     rax, [rbp+var_30]
0x18000f679  mov     [rbp+var_30], 0
0x18000f681  mov     [rbx+8], rax
0x18000f685  mov     [rcx], rax
0x18000f688  lea     rcx, [rbp+var_38]
0x18000f68c  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@std@@@std@@@std@@QEAA@XZ
0x18000f691  nop
0x18000f692  lea     rcx, [rbp+var_18]
0x18000f696  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f69b  mov     rcx, qword ptr [rbp+var_28]
0x18000f69f  test    rcx, rcx
0x18000f6a2  jz      short loc_18000F6A7
0x18000f6a4  mov     rcx, [rcx]; hHandle
0x18000f6a7  xor     r8d, r8d; bAlertable
0x18000f6aa  mov     edx, 0EA60h; dwMilliseconds
0x18000f6af  call    cs:__imp_WaitForSingleObjectEx
0x18000f6b5  cmp     eax, 102h
0x18000f6ba  jz      short loc_18000F6EF
0x18000f6bc  test    eax, eax
0x18000f6be  jnz     short loc_18000F722
0x18000f6c0  call    ?XamlThreadShutdown_WaitingForOtherXamlThread_Stop@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::XamlThreadShutdown_WaitingForOtherXamlThread_Stop(void)
0x18000f6c5  jmp     short loc_18000F6D1
0x18000f6c7  lea     rcx, [rbp+var_18]
0x18000f6cb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f6d0  nop
0x18000f6d1  lea     rcx, [rbp+var_28]
0x18000f6d5  call    ??1?$shared_ptr@VWindowingBehavior@@@std@@QEAA@XZ; std::shared_ptr<WindowingBehavior>::~shared_ptr<WindowingBehavior>(void)
0x18000f6da  mov     rcx, [rbp+var_10]
0x18000f6de  xor     rcx, rsp; StackCookie
0x18000f6e1  call    __security_check_cookie
0x18000f6e6  add     rsp, 58h
0x18000f6ea  pop     rdi
0x18000f6eb  pop     rsi
0x18000f6ec  pop     rbx
0x18000f6ed  pop     rbp
0x18000f6ee  retn
0x18000f6ef  call    ?XamlThreadShutdown_WaitingForOtherXamlThread_Timeout@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::XamlThreadShutdown_WaitingForOtherXamlThread_Timeout(void)
0x18000f6f4  nop
0x18000f6f5  mov     ecx, 80070490h
0x18000f6fa  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000f6ff  mov     r9d, eax; char *
0x18000f702  mov     rcx, [rbp+20h]; this
0x18000f706  lea     r8, aPcshellShellUx_11; "pcshell\\shell\\uxframe\\dll\\ThreadMan"...
0x18000f70d  mov     edx, 1F7h; void *
0x18000f712  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000f718  mov     rcx, [rbp+20h]; this
0x18000f71c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000f722  mov     rcx, [rbp+20h]; this
0x18000f726  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18000f72d  mov     edx, 0B0Fh; void *
0x18000f732  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
