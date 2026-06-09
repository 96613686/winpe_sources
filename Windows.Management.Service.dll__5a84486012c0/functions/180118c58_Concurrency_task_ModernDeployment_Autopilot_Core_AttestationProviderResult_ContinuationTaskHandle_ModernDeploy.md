# Concurrency::task<ModernDeployment::Autopilot::Core::AttestationProviderResult>::_ContinuationTaskHandle<ModernDeployment::Autopilot::Core::AttestationProviderResult,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (ModernDeployment::Autopilot::Core::AttestationProviderResult)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180118c58`
- end: `0x180118d82`
- name: `?_Continue@?$_ContinuationTaskHandle@UAttestationProviderResult@Core@Autopilot@ModernDeployment@@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@V?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@UAttestationProviderResult@Core@Autopilot@ModernDeployment@@@Z@6@U?$integral_constant@_N$0A@@6@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UAttestationProviderResult@Core@Autopilot@ModernDeployment@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011b090`

## callees

- `0x18000b820`
- `0x1800d84e0`
- `0x1800fbc44`
- `0x180118c58`
- `0x180119e68`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180118d11`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180118d11`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118d32`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118d32`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118cfb`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118cfb`

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
  __int128 v9; // [rsp+38h] [rbp-D0h] BYREF
  int v10; // [rsp+48h] [rbp-C0h]
  __int128 v11; // [rsp+58h] [rbp-B0h] BYREF
  int v12; // [rsp+68h] [rbp-A0h]
  __int64 v13; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v14[56]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v15; // [rsp+F0h] [rbp-18h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_OWORD *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         &v13,
         a1 + 72);
  v5 = v4;
  v15 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v14);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v15 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v9 = v3;
  if ( !v15 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v15 + 16LL))(v15, &v11, &v9);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  v9 = v11;
  v10 = v12;
  Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v14);
}

```

## disassembly

```asm
0x180118c58  mov     rax, rsp
0x180118c5b  push    rbp
0x180118c5c  push    rbx
0x180118c5d  push    rsi
0x180118c5e  push    rdi
0x180118c5f  lea     rbp, [rax-38h]
0x180118c63  sub     rsp, 118h
0x180118c6a  movaps  xmmword ptr [rax-38h], xmm6
0x180118c6e  mov     rax, cs:__security_cookie
0x180118c75  xor     rax, rsp
0x180118c78  mov     [rbp+30h+var_40], rax
0x180118c7c  mov     rdi, rcx
0x180118c7f  mov     rsi, [rcx+28h]
0x180118c83  mov     rax, [rcx+38h]
0x180118c87  movups  xmm6, xmmword ptr [rax+170h]
0x180118c8e  lea     rdx, [rcx+48h]
0x180118c92  lea     rcx, [rsp+68h]
0x180118c97  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x180118c9c  mov     rbx, rax
0x180118c9f  mov     [rbp+30h+var_48], 0
0x180118ca7  mov     rcx, [rax+38h]
0x180118cab  test    rcx, rcx
0x180118cae  jz      short loc_180118CDF
0x180118cb0  cmp     rcx, rax
0x180118cb3  jnz     short loc_180118CD3
0x180118cb5  mov     rdx, [rcx]
0x180118cb8  mov     rax, [rdx+8]
0x180118cbc  lea     rdx, [rbp+30h+var_80]
0x180118cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118cc5  mov     [rbp+30h+var_48], rax
0x180118cc9  mov     rcx, rbx
0x180118ccc  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118cd1  jmp     short loc_180118CDF
0x180118cd3  mov     [rbp+30h+var_48], rcx
0x180118cd7  mov     qword ptr [rax+38h], 0
0x180118cdf  mov     rcx, rbx
0x180118ce2  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118ce7  nop
0x180118ce8  mov     rbx, [rdi+28h]
0x180118cec  add     rbx, 160h
0x180118cf3  mov     [rsp+20h], rbx
0x180118cf8  mov     rcx, rbx
0x180118cfb  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180118d01  nop
0x180118d02  movdqa  [rsp+130h+var_108+8], xmm6
0x180118d08  mov     rcx, [rbp+30h+var_48]
0x180118d0c  test    rcx, rcx
0x180118d0f  jnz     short loc_180118D18
0x180118d11  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180118d17  int     3; Trap to Debugger
0x180118d18  mov     rax, [rcx]
0x180118d1b  lea     r8, [rsp+130h+var_108+8]
0x180118d20  lea     rdx, [rsp+130h+var_E8+8]
0x180118d25  mov     rax, [rax+10h]
0x180118d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118d2e  nop
0x180118d2f  mov     rcx, rbx
0x180118d32  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180118d38  nop
0x180118d39  movups  xmm0, [rsp+130h+var_E8+8]
0x180118d3e  movaps  [rsp+130h+var_108+8], xmm0
0x180118d43  mov     eax, [rsp+130h+var_D0]
0x180118d47  mov     [rsp+130h+var_F0], eax
0x180118d4b  lea     rdx, [rsp+130h+var_108+8]
0x180118d50  mov     rcx, rsi; this
0x180118d53  call    ?_FinalizeAndRunContinuations@?$_Task_impl@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@details@Concurrency@@QEAAXU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Z; Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>)
0x180118d58  nop
0x180118d59  lea     rcx, [rbp+30h+var_80]
0x180118d5d  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118d62  mov     rcx, [rbp+30h+var_40]
0x180118d66  xor     rcx, rsp; StackCookie
0x180118d69  call    __security_check_cookie
0x180118d6e  movaps  xmm6, [rsp+130h+var_38+8]
0x180118d76  add     rsp, 118h
0x180118d7d  pop     rdi
0x180118d7e  pop     rsi
0x180118d7f  pop     rbx
0x180118d80  pop     rbp
0x180118d81  retn
```
