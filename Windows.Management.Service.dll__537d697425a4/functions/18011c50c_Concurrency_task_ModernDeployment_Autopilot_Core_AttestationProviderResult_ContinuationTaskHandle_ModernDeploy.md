# Concurrency::task<ModernDeployment::Autopilot::Core::AttestationProviderResult>::_ContinuationTaskHandle<ModernDeployment::Autopilot::Core::AttestationProviderResult,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (ModernDeployment::Autopilot::Core::AttestationProviderResult)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18011c50c`
- end: `0x18011c649`
- name: `?_Continue@?$_ContinuationTaskHandle@UAttestationProviderResult@Core@Autopilot@ModernDeployment@@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@V?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@UAttestationProviderResult@Core@Autopilot@ModernDeployment@@@Z@6@U?$integral_constant@_N$0A@@6@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UAttestationProviderResult@Core@Autopilot@ModernDeployment@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011ea20`

## callees

- `0x18000b8f0`
- `0x1800dabf0`
- `0x1800fed34`
- `0x18011c50c`
- `0x18011d734`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18011c5cb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18011c5cb`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c5f2`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c5f2`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c5af`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c5af`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<ModernDeployment::Autopilot::Core::AttestationProviderResult>::_ContinuationTaskHandle<ModernDeployment::Autopilot::Core::AttestationProviderResult,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (ModernDeployment::Autopilot::Core::AttestationProviderResult)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  __int128 v3; // xmm6
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  __int64 v8; // rcx
  __int128 v10; // [rsp+38h] [rbp-D0h] BYREF
  int v11; // [rsp+48h] [rbp-C0h]
  __int128 v12; // [rsp+58h] [rbp-B0h] BYREF
  int v13; // [rsp+68h] [rbp-A0h]
  __int64 v14; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v15[56]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v16; // [rsp+F0h] [rbp-18h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_OWORD *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         &v14,
         a1 + 72);
  v5 = v4;
  v16 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v15);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v16 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v10 = v3;
  v8 = v16;
  if ( !v16 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v8 + 16LL))(v8, &v12, &v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  v10 = v12;
  v11 = v13;
  Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v15);
}

```

## disassembly

```asm
0x18011c50c  mov     rax, rsp
0x18011c50f  push    rbp
0x18011c510  push    rbx
0x18011c511  push    rsi
0x18011c512  push    rdi
0x18011c513  lea     rbp, [rax-38h]
0x18011c517  sub     rsp, 118h
0x18011c51e  movaps  xmmword ptr [rax-38h], xmm6
0x18011c522  mov     rax, cs:__security_cookie
0x18011c529  xor     rax, rsp
0x18011c52c  mov     [rbp+30h+var_40], rax
0x18011c530  mov     rdi, rcx
0x18011c533  mov     rsi, [rcx+28h]
0x18011c537  mov     rax, [rcx+38h]
0x18011c53b  movups  xmm6, xmmword ptr [rax+170h]
0x18011c542  lea     rdx, [rcx+48h]
0x18011c546  lea     rcx, [rsp+68h]
0x18011c54b  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x18011c550  mov     rbx, rax
0x18011c553  mov     [rbp+30h+var_48], 0
0x18011c55b  mov     rcx, [rax+38h]
0x18011c55f  test    rcx, rcx
0x18011c562  jz      short loc_18011C593
0x18011c564  cmp     rcx, rax
0x18011c567  jnz     short loc_18011C587
0x18011c569  mov     rdx, [rcx]
0x18011c56c  mov     rax, [rdx+8]
0x18011c570  lea     rdx, [rbp+30h+var_80]
0x18011c574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c579  mov     [rbp+30h+var_48], rax
0x18011c57d  mov     rcx, rbx
0x18011c580  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c585  jmp     short loc_18011C593
0x18011c587  mov     [rbp+30h+var_48], rcx
0x18011c58b  mov     qword ptr [rax+38h], 0
0x18011c593  mov     rcx, rbx
0x18011c596  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c59b  nop
0x18011c59c  mov     rbx, [rdi+28h]
0x18011c5a0  add     rbx, 160h
0x18011c5a7  mov     [rsp+20h], rbx
0x18011c5ac  mov     rcx, rbx
0x18011c5af  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18011c5b6  nop     dword ptr [rax+rax+00h]
0x18011c5bb  nop
0x18011c5bc  movdqa  [rsp+130h+var_108+8], xmm6
0x18011c5c2  mov     rcx, [rbp+30h+var_48]
0x18011c5c6  test    rcx, rcx
0x18011c5c9  jnz     short loc_18011C5D8
0x18011c5cb  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18011c5d2  nop     dword ptr [rax+rax+00h]
0x18011c5d7  int     3; Trap to Debugger
0x18011c5d8  mov     rax, [rcx]
0x18011c5db  lea     r8, [rsp+130h+var_108+8]
0x18011c5e0  lea     rdx, [rsp+130h+var_E8+8]
0x18011c5e5  mov     rax, [rax+10h]
0x18011c5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c5ee  nop
0x18011c5ef  mov     rcx, rbx
0x18011c5f2  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18011c5f9  nop     dword ptr [rax+rax+00h]
0x18011c5fe  nop
0x18011c5ff  movups  xmm0, [rsp+130h+var_E8+8]
0x18011c604  movaps  [rsp+130h+var_108+8], xmm0
0x18011c609  mov     eax, [rsp+130h+var_D0]
0x18011c60d  mov     [rsp+130h+var_F0], eax
0x18011c611  lea     rdx, [rsp+130h+var_108+8]
0x18011c616  mov     rcx, rsi; this
0x18011c619  call    ?_FinalizeAndRunContinuations@?$_Task_impl@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@details@Concurrency@@QEAAXU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Z; Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>)
0x18011c61e  nop
0x18011c61f  lea     rcx, [rbp+30h+var_80]
0x18011c623  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c628  mov     rcx, [rbp+30h+var_40]
0x18011c62c  xor     rcx, rsp; StackCookie
0x18011c62f  call    __security_check_cookie
0x18011c634  movaps  xmm6, [rsp+130h+var_38+8]
0x18011c63c  add     rsp, 118h
0x18011c643  pop     rdi
0x18011c644  pop     rsi
0x18011c645  pop     rbx
0x18011c646  pop     rbp
0x18011c647  retn
```
