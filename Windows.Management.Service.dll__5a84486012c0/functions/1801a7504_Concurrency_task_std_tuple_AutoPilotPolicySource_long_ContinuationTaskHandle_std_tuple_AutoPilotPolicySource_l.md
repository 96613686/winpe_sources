# Concurrency::task<std::tuple<AutoPilotPolicySource,long>>::_ContinuationTaskHandle<std::tuple<AutoPilotPolicySource,long>,bool,std::function<bool (std::tuple<AutoPilotPolicySource,long>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801a7504`
- end: `0x1801a761c`
- name: `?_Continue@?$_ContinuationTaskHandle@V?$tuple@W4AutoPilotPolicySource@@J@std@@_NV?$function@$$A6A_NV?$tuple@W4AutoPilotPolicySource@@J@std@@@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$tuple@W4AutoPilotPolicySource@@J@std@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801a9770`

## callees

- `0x18000b820`
- `0x1800d84e0`
- `0x1800fbc44`
- `0x180119d1c`
- `0x1801a7504`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a75c7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a75c7`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a75e4`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a75e4`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a75ae`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a75ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<std::tuple<enum AutoPilotPolicySource,long>>::_ContinuationTaskHandle<std::tuple<enum AutoPilotPolicySource,long>,bool,std::function<bool (std::tuple<enum AutoPilotPolicySource,long>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rbp
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rcx
  Concurrency::details::_TaskEventLogger *v7; // rdi
  _QWORD v9[2]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v10[64]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v11[56]; // [rsp+70h] [rbp-78h] BYREF
  __int64 v12; // [rsp+A8h] [rbp-40h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v10,
         a1 + 72);
  v5 = v4;
  v12 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v11);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v12 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  v9[1] = v7;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v9[0] = v3;
  if ( !v12 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 16LL))(v12, v9);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v11);
}

```

## disassembly

```asm
0x1801a7504  push    rbx
0x1801a7506  push    rbp
0x1801a7507  push    rsi
0x1801a7508  push    rdi
0x1801a7509  sub     rsp, 0C8h
0x1801a7510  mov     rax, cs:__security_cookie
0x1801a7517  xor     rax, rsp
0x1801a751a  mov     [rsp+0E8h+var_38], rax
0x1801a7522  mov     rsi, rcx
0x1801a7525  mov     rbp, [rcx+28h]
0x1801a7529  mov     rbx, [rcx+38h]
0x1801a752d  mov     rbx, [rbx+170h]
0x1801a7534  lea     rdx, [rcx+48h]
0x1801a7538  lea     rcx, [rsp+0E8h+var_B8]
0x1801a753d  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x1801a7542  mov     rdi, rax
0x1801a7545  mov     [rsp+0E8h+var_40], 0
0x1801a7551  mov     rcx, [rax+38h]
0x1801a7555  test    rcx, rcx
0x1801a7558  jz      short loc_1801A7592
0x1801a755a  cmp     rcx, rax
0x1801a755d  jnz     short loc_1801A7582
0x1801a755f  mov     rdx, [rcx]
0x1801a7562  mov     rax, [rdx+8]
0x1801a7566  lea     rdx, [rsp+0E8h+var_78]
0x1801a756b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7570  mov     [rsp+0E8h+var_40], rax
0x1801a7578  mov     rcx, rdi
0x1801a757b  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a7580  jmp     short loc_1801A7592
0x1801a7582  mov     [rsp+0E8h+var_40], rcx
0x1801a758a  mov     qword ptr [rax+38h], 0
0x1801a7592  mov     rcx, rdi
0x1801a7595  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a759a  nop
0x1801a759b  mov     rdi, [rsi+28h]
0x1801a759f  add     rdi, 160h
0x1801a75a6  mov     [rsp+0E8h+var_C0], rdi
0x1801a75ab  mov     rcx, rdi
0x1801a75ae  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801a75b4  nop
0x1801a75b5  mov     [rsp+0E8h+var_C8], rbx
0x1801a75ba  mov     rcx, [rsp+0E8h+var_40]
0x1801a75c2  test    rcx, rcx
0x1801a75c5  jnz     short loc_1801A75CE
0x1801a75c7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801a75cd  int     3; Trap to Debugger
0x1801a75ce  mov     rax, [rcx]
0x1801a75d1  lea     rdx, [rsp+0E8h+var_C8]
0x1801a75d6  mov     rax, [rax+10h]
0x1801a75da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a75df  mov     bl, al
0x1801a75e1  mov     rcx, rdi
0x1801a75e4  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801a75ea  nop
0x1801a75eb  mov     dl, bl
0x1801a75ed  mov     rcx, rbp; this
0x1801a75f0  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801a75f5  nop
0x1801a75f6  lea     rcx, [rsp+0E8h+var_78]
0x1801a75fb  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801a7600  mov     rcx, [rsp+0E8h+var_38]
0x1801a7608  xor     rcx, rsp; StackCookie
0x1801a760b  call    __security_check_cookie
0x1801a7610  add     rsp, 0C8h
0x1801a7617  pop     rdi
0x1801a7618  pop     rsi
0x1801a7619  pop     rbp
0x1801a761a  pop     rbx
0x1801a761b  retn
```
