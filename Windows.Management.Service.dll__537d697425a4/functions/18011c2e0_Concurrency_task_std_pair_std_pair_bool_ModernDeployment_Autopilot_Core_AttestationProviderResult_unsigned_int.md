# Concurrency::task<std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>>::_ContinuationTaskHandle<std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18011c2e0`
- end: `0x18011c432`
- name: `?_Continue@?$_ContinuationTaskHandle@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@std@@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@2@V?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@std@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011e990`

## callees

- `0x18000b8f0`
- `0x1800dabf0`
- `0x1800fed34`
- `0x18011c2e0`
- `0x18011d734`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18011c3ae`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18011c3ae`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c3d5`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c3d5`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c38e`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c38e`

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
  __int64 v10; // rcx
  __int128 v12; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v13; // [rsp+48h] [rbp-C0h]
  __int128 v14; // [rsp+58h] [rbp-B0h] BYREF
  int v15; // [rsp+68h] [rbp-A0h]
  _BYTE v16[72]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v17[56]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F0h] [rbp-18h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_QWORD *)(a1 + 56);
  v4 = *(_OWORD *)(v3 + 368);
  v5 = *(_OWORD *)(v3 + 384);
  v6 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v16,
         a1 + 72);
  v7 = v6;
  v18 = 0;
  v8 = *(_QWORD *)(v6 + 56);
  if ( v8 )
  {
    if ( v8 == v6 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v8 + 8LL))(v8, v17);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v7);
    }
    else
    {
      v18 = *(_QWORD *)(v6 + 56);
      *(_QWORD *)(v6 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v7);
  v9 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v9);
  v12 = v4;
  v13 = v5;
  v10 = v18;
  if ( !v18 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v10 + 16LL))(v10, &v14, &v12);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v9);
  v12 = v14;
  LODWORD(v13) = v15;
  Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v17);
}

```

## disassembly

```asm
0x18011c2e0  mov     rax, rsp
0x18011c2e3  push    rbp
0x18011c2e4  push    rbx
0x18011c2e5  push    rsi
0x18011c2e6  push    rdi
0x18011c2e7  lea     rbp, [rax-48h]
0x18011c2eb  sub     rsp, 128h
0x18011c2f2  movaps  xmmword ptr [rax-38h], xmm6
0x18011c2f6  movaps  xmmword ptr [rax-48h], xmm7
0x18011c2fa  mov     rax, cs:__security_cookie
0x18011c301  xor     rax, rsp
0x18011c304  mov     [rbp+40h+var_50], rax
0x18011c308  mov     rdi, rcx
0x18011c30b  mov     rsi, [rcx+28h]
0x18011c30f  mov     rax, [rcx+38h]
0x18011c313  movups  xmm6, xmmword ptr [rax+170h]
0x18011c31a  movups  xmm7, xmmword ptr [rax+180h]
0x18011c321  lea     rdx, [rcx+48h]
0x18011c325  lea     rcx, [rsp+140h+var_D8]
0x18011c32a  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x18011c32f  mov     rbx, rax
0x18011c332  mov     [rbp+40h+var_58], 0
0x18011c33a  mov     rcx, [rax+38h]
0x18011c33e  test    rcx, rcx
0x18011c341  jz      short loc_18011C372
0x18011c343  cmp     rcx, rax
0x18011c346  jnz     short loc_18011C366
0x18011c348  mov     rdx, [rcx]
0x18011c34b  mov     rax, [rdx+8]
0x18011c34f  lea     rdx, [rbp+40h+var_90]
0x18011c353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c358  mov     [rbp+40h+var_58], rax
0x18011c35c  mov     rcx, rbx
0x18011c35f  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c364  jmp     short loc_18011C372
0x18011c366  mov     [rbp+40h+var_58], rcx
0x18011c36a  mov     qword ptr [rax+38h], 0
0x18011c372  mov     rcx, rbx
0x18011c375  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c37a  nop
0x18011c37b  mov     rbx, [rdi+28h]
0x18011c37f  add     rbx, 160h
0x18011c386  mov     [rsp+140h+var_120], rbx
0x18011c38b  mov     rcx, rbx
0x18011c38e  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18011c395  nop     dword ptr [rax+rax+00h]
0x18011c39a  nop
0x18011c39b  movaps  [rsp+140h+var_118+8], xmm6
0x18011c3a0  movaps  [rsp+140h+var_108+8], xmm7
0x18011c3a5  mov     rcx, [rbp+40h+var_58]
0x18011c3a9  test    rcx, rcx
0x18011c3ac  jnz     short loc_18011C3BB
0x18011c3ae  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18011c3b5  nop     dword ptr [rax+rax+00h]
0x18011c3ba  int     3; Trap to Debugger
0x18011c3bb  mov     rax, [rcx]
0x18011c3be  lea     r8, [rsp+140h+var_118+8]
0x18011c3c3  lea     rdx, [rsp+140h+var_F8+8]
0x18011c3c8  mov     rax, [rax+10h]
0x18011c3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c3d1  nop
0x18011c3d2  mov     rcx, rbx
0x18011c3d5  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18011c3dc  nop     dword ptr [rax+rax+00h]
0x18011c3e1  nop
0x18011c3e2  movups  xmm0, xmmword ptr [rsp+140h+var_F8+8]
0x18011c3e7  movaps  [rsp+140h+var_118+8], xmm0
0x18011c3ec  mov     eax, [rsp+140h+var_E0]
0x18011c3f0  mov     dword ptr [rsp+140h+var_108+8], eax
0x18011c3f4  lea     rdx, [rsp+140h+var_118+8]
0x18011c3f9  mov     rcx, rsi; this
0x18011c3fc  call    ?_FinalizeAndRunContinuations@?$_Task_impl@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@details@Concurrency@@QEAAXU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Z; Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>)
0x18011c401  nop
0x18011c402  lea     rcx, [rbp+40h+var_90]
0x18011c406  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c40b  mov     rcx, [rbp+40h+var_50]
0x18011c40f  xor     rcx, rsp; StackCookie
0x18011c412  call    __security_check_cookie
0x18011c417  lea     r11, [rsp+140h+var_18]
0x18011c41f  movaps  xmm6, xmmword ptr [r11-18h]
0x18011c424  movaps  xmm7, xmmword ptr [r11-28h]
0x18011c429  mov     rsp, r11
0x18011c42c  pop     rdi
0x18011c42d  pop     rsi
0x18011c42e  pop     rbx
0x18011c42f  pop     rbp
0x18011c430  retn
```
