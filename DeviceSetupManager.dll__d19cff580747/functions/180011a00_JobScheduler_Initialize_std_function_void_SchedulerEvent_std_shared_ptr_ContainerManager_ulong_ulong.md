# JobScheduler::Initialize(std::function<void (SchedulerEvent)>,std::shared_ptr<ContainerManager>,ulong,ulong)

- ea: `0x180011a00`
- end: `0x180011c93`
- name: `?Initialize@JobScheduler@@QEAAJV?$function@$$A6AXW4SchedulerEvent@@@Z@std@@V?$shared_ptr@VContainerManager@@@3@KK@Z`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024374`

## callees

- `0x18000fa64`
- `0x18000fa88`
- `0x18000fa98`
- `0x1800103cc`
- `0x1800104fc`
- `0x1800112c8`
- `0x18001184c`
- `0x1800119cc`
- `0x180011a00`
- `0x18001370c`
- `0x180013864`
- `0x180013b14`
- `0x180015404`
- `0x180015494`
- `0x1800190bc`
- `0x18001af70`
- `0x180021790`
- `0x1800226b4`
- `0x18002b064`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180011b75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180011b75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180011b66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x180011b66`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180011af8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180011ad7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180011ad7`

## string_xrefs

- `0x180011b2e`: `onecoreuap\base\devices\setup\dsm\service\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobScheduler::Initialize(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  const char *v10; // r9
  struct _TP_POOL *Threadpool; // r14
  unsigned int LastError; // ebx
  const char *v13; // r9
  std::_Ref_count_base *v14; // rcx
  __int64 result; // rax
  _QWORD *v16; // rax
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // rcx
  _BYTE v19[8]; // [rsp+30h] [rbp-D8h] BYREF
  std::_Ref_count_base *v20; // [rsp+38h] [rbp-D0h]
  __int64 v21; // [rsp+40h] [rbp-C8h] BYREF
  void (__stdcall *v22)(PTP_POOL); // [rsp+48h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B8h]
  __int64 v24; // [rsp+58h] [rbp-B0h]
  _BYTE v25[128]; // [rsp+60h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v23 = a2;
  v24 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
  }
  v6 = (__int64 *)std::shared_ptr<Container>::shared_ptr<Container>(v19, a3);
  v7 = *v6;
  *v6 = *(_QWORD *)(a1 + 456);
  *(_QWORD *)(a1 + 456) = v7;
  v8 = v6[1];
  v6[1] = *(_QWORD *)(a1 + 464);
  *(_QWORD *)(a1 + 464) = v8;
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  try
  {
    v9 = std::function<void (enum SchedulerEvent)>::function<void (enum SchedulerEvent)>(v25, a2);
    std::_Func_class<void,enum SchedulerEvent>::_Swap(v9, a1 + 472);
    std::_Func_class<void,enum SchedulerEvent>::_Tidy(v25);
    Threadpool = CreateThreadpool(0);
    if ( *(_QWORD *)(a1 + 16) )
    {
      v21 = *(_QWORD *)(a1 + 16);
      wil::last_error_context::last_error_context((wil::last_error_context *)v19);
      v22 = CloseThreadpool;
      wistd::invoke<void (*)(_TP_POOL *),_TP_POOL * &>(&v22, &v21);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v19);
    }
    *(_QWORD *)(a1 + 16) = Threadpool;
    if ( Threadpool )
    {
      SetThreadpoolThreadMinimum(Threadpool, 1u);
      SetThreadpoolThreadMaximum(*(PTP_POOL *)(a1 + 16), 4u);
      std::enable_shared_from_this<JobScheduler>::shared_from_this(a1, v19);
      JobScheduler::WorkContext::Initialize((PVOID)(a1 + 24));
      std::enable_shared_from_this<JobScheduler>::shared_from_this(a1, v19);
      JobScheduler::WorkContext::Initialize((PVOID)(a1 + 168));
      std::enable_shared_from_this<JobScheduler>::shared_from_this(a1, v19);
      JobScheduler::WorkContext::Initialize((PVOID)(a1 + 312));
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        a1 + 568,
        1);
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        a1 + 576,
        0);
      v16 = (_QWORD *)lambda_5bb2a98cf85b373dd723daae1fbe55f9_::_lambda_5bb2a98cf85b373dd723daae1fbe55f9_(v19, a1);
      wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_4b4846d16720e5e9fa5b480fd6481bd4__void_(
        v25,
        *v16);
      wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
        a1 + 536,
        v25);
      wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(v25);
      std::_Func_class<void,enum SchedulerEvent>::_Tidy(a2);
      v17 = *(std::_Ref_count_base **)(a3 + 8);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      result = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x13,
                    (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\scheduler.cpp",
                    v10);
      std::_Func_class<void,enum SchedulerEvent>::_Tidy(a2);
      v14 = *(std::_Ref_count_base **)(a3 + 8);
      if ( v14 )
        std::_Ref_count_base::_Decref(v14);
      result = LastError;
    }
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x40,
                     (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\scheduler.cpp",
                     v13);
    std::_Func_class<void,enum SchedulerEvent>::_Tidy(v23);
    v18 = *(std::_Ref_count_base **)(v24 + 8);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    return (unsigned int)v21;
  }
  return result;
}

```

## disassembly

```asm
0x180011a00  mov     [rsp+arg_18], rbx
0x180011a05  push    rsi
0x180011a06  push    rdi
0x180011a07  push    r14
0x180011a09  sub     rsp, 0F0h
0x180011a10  mov     rax, cs:__security_cookie
0x180011a17  xor     rax, rsp
0x180011a1a  mov     [rsp+108h+var_28], rax
0x180011a22  mov     rsi, r8
0x180011a25  mov     rdi, rdx
0x180011a28  mov     rbx, rcx
0x180011a2b  mov     [rsp+108h+var_B8], rdx
0x180011a30  mov     [rsp+108h+var_B0], r8
0x180011a35  lea     rax, WPP_GLOBAL_Control
0x180011a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a43  cmp     rcx, rax
0x180011a46  jz      short loc_180011A69
0x180011a48  test    byte ptr [rcx+1Ch], 80h
0x180011a4c  jz      short loc_180011A69
0x180011a4e  cmp     byte ptr [rcx+19h], 4
0x180011a52  jb      short loc_180011A69
0x180011a54  mov     edx, 0Ah
0x180011a59  lea     r8, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x180011a60  mov     rcx, [rcx+10h]
0x180011a64  call    WPP_SF_
0x180011a69  mov     rdx, rsi
0x180011a6c  lea     rcx, [rsp+108h+var_D8]
0x180011a71  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x180011a76  mov     rdx, [rax]
0x180011a79  mov     rcx, [rbx+1C8h]
0x180011a80  mov     [rax], rcx
0x180011a83  mov     [rbx+1C8h], rdx
0x180011a8a  mov     rdx, [rax+8]
0x180011a8e  mov     rcx, [rbx+1D0h]
0x180011a95  mov     [rax+8], rcx
0x180011a99  mov     [rbx+1D0h], rdx
0x180011aa0  mov     rcx, [rsp+108h+var_D0]; this
0x180011aa5  test    rcx, rcx
0x180011aa8  jz      short loc_180011AAF
0x180011aaa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011aaf  mov     rdx, rdi
0x180011ab2  lea     rcx, [rsp+108h+var_A8]
0x180011ab7  call    ??0?$function@$$A6AXW4SchedulerEvent@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (SchedulerEvent)>::function<void (SchedulerEvent)>(std::function<void (SchedulerEvent)> const &)
0x180011abc  lea     rdx, [rbx+1D8h]
0x180011ac3  mov     rcx, rax
0x180011ac6  call    ?_Swap@?$_Func_class@XW4SchedulerEvent@@@std@@IEAAXAEAV12@@Z; std::_Func_class<void,SchedulerEvent>::_Swap(std::_Func_class<void,SchedulerEvent> &)
0x180011acb  lea     rcx, [rsp+108h+var_A8]
0x180011ad0  call    ?_Tidy@?$_Func_class@XW4SchedulerEvent@@@std@@IEAAXXZ; std::_Func_class<void,SchedulerEvent>::_Tidy(void)
0x180011ad5  xor     ecx, ecx; reserved
0x180011ad7  call    cs:__imp_CreateThreadpool
0x180011add  mov     r14, rax
0x180011ae0  mov     rax, [rbx+10h]
0x180011ae4  test    rax, rax
0x180011ae7  jz      short loc_180011B1D
0x180011ae9  mov     [rsp+108h+var_C8], rax
0x180011aee  lea     rcx, [rsp+108h+var_D8]; this
0x180011af3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011af8  mov     rcx, cs:__imp_CloseThreadpool
0x180011aff  mov     [rsp+108h+var_C0], rcx
0x180011b04  lea     rdx, [rsp+108h+var_C8]
0x180011b09  lea     rcx, [rsp+108h+var_C0]
0x180011b0e  call    ??$invoke@P6AXPEAU_TP_POOL@@@ZAEAPEAU1@@wistd@@YAX$$QEAP6AXPEAU_TP_POOL@@@ZAEAPEAU1@@Z; wistd::invoke<void (*)(_TP_POOL *),_TP_POOL * &>(void (*&&)(_TP_POOL *),_TP_POOL * &)
0x180011b13  lea     rcx, [rsp+108h+var_D8]; this
0x180011b18  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011b1d  mov     [rbx+10h], r14
0x180011b21  test    r14, r14
0x180011b24  jnz     short loc_180011B5E
0x180011b26  mov     rcx, [rsp+108h]; this
0x180011b2e  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180011b35  lea     edx, [r14+13h]; void *
0x180011b39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011b3e  mov     ebx, eax
0x180011b40  mov     rcx, rdi
0x180011b43  call    ?_Tidy@?$_Func_class@XW4SchedulerEvent@@@std@@IEAAXXZ; std::_Func_class<void,SchedulerEvent>::_Tidy(void)
0x180011b48  nop
0x180011b49  mov     rcx, [rsi+8]; this
0x180011b4d  test    rcx, rcx
0x180011b50  jz      short loc_180011B57
0x180011b52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011b57  mov     eax, ebx
0x180011b59  jmp     loc_180011C6F
0x180011b5e  mov     edx, 1; cthrdMic
0x180011b63  mov     rcx, r14; ptpp
0x180011b66  call    cs:__imp_SetThreadpoolThreadMinimum
0x180011b6c  mov     edx, 4; cthrdMost
0x180011b71  mov     rcx, [rbx+10h]; ptpp
0x180011b75  call    cs:__imp_SetThreadpoolThreadMaximum
0x180011b7b  lea     rdx, [rsp+108h+var_D8]
0x180011b80  mov     rcx, rbx
0x180011b83  call    ?shared_from_this@?$enable_shared_from_this@VJobScheduler@@@std@@QEAA?AV?$shared_ptr@VJobScheduler@@@2@XZ; std::enable_shared_from_this<JobScheduler>::shared_from_this(void)
0x180011b88  lea     rcx, [rbx+18h]; pv
0x180011b8c  xor     r8d, r8d
0x180011b8f  mov     rdx, rax
0x180011b92  call    ?Initialize@WorkContext@JobScheduler@@QEAAXV?$shared_ptr@VJobScheduler@@@std@@W4_TP_CALLBACK_PRIORITY@@@Z; JobScheduler::WorkContext::Initialize(std::shared_ptr<JobScheduler>,_TP_CALLBACK_PRIORITY)
0x180011b97  lea     rdx, [rsp+108h+var_D8]
0x180011b9c  mov     rcx, rbx
0x180011b9f  call    ?shared_from_this@?$enable_shared_from_this@VJobScheduler@@@std@@QEAA?AV?$shared_ptr@VJobScheduler@@@2@XZ; std::enable_shared_from_this<JobScheduler>::shared_from_this(void)
0x180011ba4  lea     rcx, [rbx+0A8h]; pv
0x180011bab  mov     r8d, 1
0x180011bb1  mov     rdx, rax
0x180011bb4  call    ?Initialize@WorkContext@JobScheduler@@QEAAXV?$shared_ptr@VJobScheduler@@@std@@W4_TP_CALLBACK_PRIORITY@@@Z; JobScheduler::WorkContext::Initialize(std::shared_ptr<JobScheduler>,_TP_CALLBACK_PRIORITY)
0x180011bb9  lea     rdx, [rsp+108h+var_D8]
0x180011bbe  mov     rcx, rbx
0x180011bc1  call    ?shared_from_this@?$enable_shared_from_this@VJobScheduler@@@std@@QEAA?AV?$shared_ptr@VJobScheduler@@@2@XZ; std::enable_shared_from_this<JobScheduler>::shared_from_this(void)
0x180011bc6  lea     rcx, [rbx+138h]; pv
0x180011bcd  mov     r8d, 2
0x180011bd3  mov     rdx, rax
0x180011bd6  call    ?Initialize@WorkContext@JobScheduler@@QEAAXV?$shared_ptr@VJobScheduler@@@std@@W4_TP_CALLBACK_PRIORITY@@@Z; JobScheduler::WorkContext::Initialize(std::shared_ptr<JobScheduler>,_TP_CALLBACK_PRIORITY)
0x180011bdb  lea     rcx, [rbx+238h]
0x180011be2  mov     edx, 1
0x180011be7  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011bec  lea     rcx, [rbx+240h]
0x180011bf3  xor     edx, edx
0x180011bf5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180011bfa  mov     rdx, rbx
0x180011bfd  lea     rcx, [rsp+108h+var_D8]
0x180011c02  call    _lambda_5bb2a98cf85b373dd723daae1fbe55f9____lambda_5bb2a98cf85b373dd723daae1fbe55f9_
0x180011c07  mov     rdx, [rax]
0x180011c0a  lea     rcx, [rsp+108h+var_A8]
0x180011c0f  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_4b4846d16720e5e9fa5b480fd6481bd4__void_
0x180011c14  nop
0x180011c15  lea     rcx, [rbx+218h]
0x180011c1c  lea     rdx, [rsp+108h+var_A8]
0x180011c21  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180011c26  nop
0x180011c27  lea     rcx, [rsp+108h+var_A8]
0x180011c2c  call    ??1?$function@$$A6AXAEBU_DRIVER_RECOVERY_CONTEXT@@@Z@wistd@@QEAA@XZ; wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(void)
0x180011c31  nop
0x180011c32  mov     rcx, rdi
0x180011c35  call    ?_Tidy@?$_Func_class@XW4SchedulerEvent@@@std@@IEAAXXZ; std::_Func_class<void,SchedulerEvent>::_Tidy(void)
0x180011c3a  nop
0x180011c3b  mov     rcx, [rsi+8]; this
0x180011c3f  test    rcx, rcx
0x180011c42  jz      short loc_180011C49
0x180011c44  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011c49  xor     eax, eax
0x180011c4b  jmp     short loc_180011C6F
0x180011c4d  mov     rcx, [rsp+108h+var_B8]
0x180011c52  call    ?_Tidy@?$_Func_class@XW4SchedulerEvent@@@std@@IEAAXXZ; std::_Func_class<void,SchedulerEvent>::_Tidy(void)
0x180011c57  nop
0x180011c58  mov     rax, [rsp+108h+var_B0]
0x180011c5d  mov     rcx, [rax+8]; this
0x180011c61  test    rcx, rcx
0x180011c64  jz      short loc_180011C6B
0x180011c66  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011c6b  mov     eax, dword ptr [rsp+108h+var_C8]
0x180011c6f  mov     rcx, [rsp+108h+var_28]
0x180011c77  xor     rcx, rsp; StackCookie
0x180011c7a  call    __security_check_cookie
0x180011c7f  mov     rbx, [rsp+108h+arg_18]
0x180011c87  add     rsp, 0F0h
0x180011c8e  pop     r14
0x180011c90  pop     rdi
0x180011c91  pop     rsi
0x180011c92  retn
```
