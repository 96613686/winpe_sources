# Concurrency::task<std::tuple<AutoPilotPolicySource,long>>::_ContinuationTaskHandle<std::tuple<AutoPilotPolicySource,long>,bool,std::function<bool (std::tuple<AutoPilotPolicySource,long>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801acdb4`
- end: `0x1801acedf`
- name: `?_Continue@?$_ContinuationTaskHandle@V?$tuple@W4AutoPilotPolicySource@@J@std@@_NV?$function@$$A6A_NV?$tuple@W4AutoPilotPolicySource@@J@std@@@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$tuple@W4AutoPilotPolicySource@@J@std@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801af170`

## callees

- `0x18000b8f0`
- `0x1800dabf0`
- `0x1800fed34`
- `0x18011d5b4`
- `0x1801acdb4`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801ace7d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801ace7d`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acea0`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acea0`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801ace5e`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801ace5e`

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
  __int64 v8; // rcx
  _QWORD v10[2]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v11[64]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v12[56]; // [rsp+70h] [rbp-78h] BYREF
  __int64 v13; // [rsp+A8h] [rbp-40h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v11,
         a1 + 72);
  v5 = v4;
  v13 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v12);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v13 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  v10[1] = v7;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v10[0] = v3;
  v8 = v13;
  if ( !v13 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 16LL))(v8, v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v12);
}

```

## disassembly

```asm
0x1801acdb4  push    rbx
0x1801acdb6  push    rbp
0x1801acdb7  push    rsi
0x1801acdb8  push    rdi
0x1801acdb9  sub     rsp, 0C8h
0x1801acdc0  mov     rax, cs:__security_cookie
0x1801acdc7  xor     rax, rsp
0x1801acdca  mov     [rsp+0E8h+var_38], rax
0x1801acdd2  mov     rsi, rcx
0x1801acdd5  mov     rbp, [rcx+28h]
0x1801acdd9  mov     rbx, [rcx+38h]
0x1801acddd  mov     rbx, [rbx+170h]
0x1801acde4  lea     rdx, [rcx+48h]
0x1801acde8  lea     rcx, [rsp+0E8h+var_B8]
0x1801acded  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x1801acdf2  mov     rdi, rax
0x1801acdf5  mov     [rsp+0E8h+var_40], 0
0x1801ace01  mov     rcx, [rax+38h]
0x1801ace05  test    rcx, rcx
0x1801ace08  jz      short loc_1801ACE42
0x1801ace0a  cmp     rcx, rax
0x1801ace0d  jnz     short loc_1801ACE32
0x1801ace0f  mov     rdx, [rcx]
0x1801ace12  mov     rax, [rdx+8]
0x1801ace16  lea     rdx, [rsp+0E8h+var_78]
0x1801ace1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ace20  mov     [rsp+0E8h+var_40], rax
0x1801ace28  mov     rcx, rdi
0x1801ace2b  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801ace30  jmp     short loc_1801ACE42
0x1801ace32  mov     [rsp+0E8h+var_40], rcx
0x1801ace3a  mov     qword ptr [rax+38h], 0
0x1801ace42  mov     rcx, rdi
0x1801ace45  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801ace4a  nop
0x1801ace4b  mov     rdi, [rsi+28h]
0x1801ace4f  add     rdi, 160h
0x1801ace56  mov     [rsp+0E8h+var_C0], rdi
0x1801ace5b  mov     rcx, rdi
0x1801ace5e  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801ace65  nop     dword ptr [rax+rax+00h]
0x1801ace6a  nop
0x1801ace6b  mov     [rsp+0E8h+var_C8], rbx
0x1801ace70  mov     rcx, [rsp+0E8h+var_40]
0x1801ace78  test    rcx, rcx
0x1801ace7b  jnz     short loc_1801ACE8A
0x1801ace7d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801ace84  nop     dword ptr [rax+rax+00h]
0x1801ace89  int     3; Trap to Debugger
0x1801ace8a  mov     rax, [rcx]
0x1801ace8d  lea     rdx, [rsp+0E8h+var_C8]
0x1801ace92  mov     rax, [rax+10h]
0x1801ace96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ace9b  mov     bl, al
0x1801ace9d  mov     rcx, rdi
0x1801acea0  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801acea7  nop     dword ptr [rax+rax+00h]
0x1801aceac  nop
0x1801acead  mov     dl, bl
0x1801aceaf  mov     rcx, rbp; this
0x1801aceb2  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801aceb7  nop
0x1801aceb8  lea     rcx, [rsp+0E8h+var_78]
0x1801acebd  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801acec2  mov     rcx, [rsp+0E8h+var_38]
0x1801aceca  xor     rcx, rsp; StackCookie
0x1801acecd  call    __security_check_cookie
0x1801aced2  add     rsp, 0C8h
0x1801aced9  pop     rdi
0x1801aceda  pop     rsi
0x1801acedb  pop     rbp
0x1801acedc  pop     rbx
0x1801acedd  retn
```
