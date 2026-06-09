# Concurrency::task<std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>>::_ContinuationTaskHandle<std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180118a3c`
- end: `0x180118b7b`
- name: `?_Continue@?$_ContinuationTaskHandle@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@std@@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@2@V?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@std@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011b010`

## callees

- `0x18000b820`
- `0x1800d84e0`
- `0x1800fbc44`
- `0x180118a3c`
- `0x180119e68`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180118b04`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180118b04`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118b25`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118b25`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118aea`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118aea`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>>::_ContinuationTaskHandle<std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rsi
  __int64 v3; // rax
  __int128 v4; // xmm6
  __int128 v5; // xmm7
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  Concurrency::details::_TaskEventLogger *v9; // rbx
  __int128 v11; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v12; // [rsp+48h] [rbp-C0h]
  __int128 v13; // [rsp+58h] [rbp-B0h] BYREF
  int v14; // [rsp+68h] [rbp-A0h]
  _BYTE v15[72]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v16[56]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-18h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_QWORD *)(a1 + 56);
  v4 = *(_OWORD *)(v3 + 368);
  v5 = *(_OWORD *)(v3 + 384);
  v6 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v15,
         a1 + 72);
  v7 = v6;
  v17 = 0;
  v8 = *(_QWORD *)(v6 + 56);
  if ( v8 )
  {
    if ( v8 == v6 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 8LL))(v8, v16);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v7);
    }
    else
    {
      v17 = *(_QWORD *)(v6 + 56);
      *(_QWORD *)(v6 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v7);
  v9 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v9);
  v11 = v4;
  v12 = v5;
  if ( !v17 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v17 + 16LL))(v17, &v13, &v11);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v9);
  v11 = v13;
  LODWORD(v12) = v14;
  Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v16);
}

```

## disassembly

```asm
0x180118a3c  mov     rax, rsp
0x180118a3f  push    rbp
0x180118a40  push    rbx
0x180118a41  push    rsi
0x180118a42  push    rdi
0x180118a43  lea     rbp, [rax-48h]
0x180118a47  sub     rsp, 128h
0x180118a4e  movaps  xmmword ptr [rax-38h], xmm6
0x180118a52  movaps  xmmword ptr [rax-48h], xmm7
0x180118a56  mov     rax, cs:__security_cookie
0x180118a5d  xor     rax, rsp
0x180118a60  mov     [rbp+40h+var_50], rax
0x180118a64  mov     rdi, rcx
0x180118a67  mov     rsi, [rcx+28h]
0x180118a6b  mov     rax, [rcx+38h]
0x180118a6f  movups  xmm6, xmmword ptr [rax+170h]
0x180118a76  movups  xmm7, xmmword ptr [rax+180h]
0x180118a7d  lea     rdx, [rcx+48h]
0x180118a81  lea     rcx, [rsp+140h+var_D8]
0x180118a86  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x180118a8b  mov     rbx, rax
0x180118a8e  mov     [rbp+40h+var_58], 0
0x180118a96  mov     rcx, [rax+38h]
0x180118a9a  test    rcx, rcx
0x180118a9d  jz      short loc_180118ACE
0x180118a9f  cmp     rcx, rax
0x180118aa2  jnz     short loc_180118AC2
0x180118aa4  mov     rdx, [rcx]
0x180118aa7  mov     rax, [rdx+8]
0x180118aab  lea     rdx, [rbp+40h+var_90]
0x180118aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118ab4  mov     [rbp+40h+var_58], rax
0x180118ab8  mov     rcx, rbx
0x180118abb  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118ac0  jmp     short loc_180118ACE
0x180118ac2  mov     [rbp+40h+var_58], rcx
0x180118ac6  mov     qword ptr [rax+38h], 0
0x180118ace  mov     rcx, rbx
0x180118ad1  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118ad6  nop
0x180118ad7  mov     rbx, [rdi+28h]
0x180118adb  add     rbx, 160h
0x180118ae2  mov     [rsp+140h+var_120], rbx
0x180118ae7  mov     rcx, rbx
0x180118aea  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180118af0  nop
0x180118af1  movaps  [rsp+140h+var_118+8], xmm6
0x180118af6  movaps  [rsp+140h+var_108+8], xmm7
0x180118afb  mov     rcx, [rbp+40h+var_58]
0x180118aff  test    rcx, rcx
0x180118b02  jnz     short loc_180118B0B
0x180118b04  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180118b0a  int     3; Trap to Debugger
0x180118b0b  mov     rax, [rcx]
0x180118b0e  lea     r8, [rsp+140h+var_118+8]
0x180118b13  lea     rdx, [rsp+140h+var_F8+8]
0x180118b18  mov     rax, [rax+10h]
0x180118b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118b21  nop
0x180118b22  mov     rcx, rbx
0x180118b25  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180118b2b  nop
0x180118b2c  movups  xmm0, xmmword ptr [rsp+140h+var_F8+8]
0x180118b31  movaps  [rsp+140h+var_118+8], xmm0
0x180118b36  mov     eax, [rsp+140h+var_E0]
0x180118b3a  mov     dword ptr [rsp+140h+var_108+8], eax
0x180118b3e  lea     rdx, [rsp+140h+var_118+8]
0x180118b43  mov     rcx, rsi; this
0x180118b46  call    ?_FinalizeAndRunContinuations@?$_Task_impl@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@details@Concurrency@@QEAAXU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Z; Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>)
0x180118b4b  nop
0x180118b4c  lea     rcx, [rbp+40h+var_90]
0x180118b50  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118b55  mov     rcx, [rbp+40h+var_50]
0x180118b59  xor     rcx, rsp; StackCookie
0x180118b5c  call    __security_check_cookie
0x180118b61  lea     r11, [rsp+140h+var_18]
0x180118b69  movaps  xmm6, xmmword ptr [r11-18h]
0x180118b6e  movaps  xmm7, xmmword ptr [r11-28h]
0x180118b73  mov     rsp, r11
0x180118b76  pop     rdi
0x180118b77  pop     rsi
0x180118b78  pop     rbx
0x180118b79  pop     rbp
0x180118b7a  retn
```
