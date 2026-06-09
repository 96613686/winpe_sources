# Concurrency::task<bool>::_ContinuationTaskHandle<bool,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (bool)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18011c650`
- end: `0x18011c78f`
- name: `?_Continue@?$_ContinuationTaskHandle@_NU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@V?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_N@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@_N@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011eab0`

## callees

- `0x18000b8f0`
- `0x1800dabf0`
- `0x1800fed34`
- `0x18011c650`
- `0x18011d734`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18011c711`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18011c711`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c738`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c738`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c6f6`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011c6f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::task<bool>::_ContinuationTaskHandle<bool,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (bool)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // r14
  char v3; // si
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v6; // rcx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  __int64 v8; // rcx
  _BYTE v10[8]; // [rsp+20h] [rbp-99h] BYREF
  Concurrency::details::_TaskEventLogger *v11; // [rsp+28h] [rbp-91h]
  __int128 v12; // [rsp+30h] [rbp-89h] BYREF
  int v13; // [rsp+40h] [rbp-79h]
  __int128 v14; // [rsp+50h] [rbp-69h]
  int v15; // [rsp+60h] [rbp-59h]
  _BYTE v16[64]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v17[56]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v18; // [rsp+E8h] [rbp+2Fh]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_BYTE *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v16,
         a1 + 72);
  v5 = v4;
  v18 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v17);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v18 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  v11 = v7;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v10[0] = v3;
  v8 = v18;
  if ( !v18 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *, _BYTE *))(*(_QWORD *)v8 + 16LL))(v8, &v12, v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  v14 = v12;
  v15 = v13;
  Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v17);
}

```

## disassembly

```asm
0x18011c650  mov     [rsp-8+arg_8], rbx
0x18011c655  mov     [rsp-8+arg_10], rsi
0x18011c65a  push    rbp
0x18011c65b  push    rdi
0x18011c65c  push    r14
0x18011c65e  lea     rbp, [rsp-47h]
0x18011c663  sub     rsp, 100h
0x18011c66a  mov     rax, cs:__security_cookie
0x18011c671  xor     rax, rsp
0x18011c674  mov     [rbp+57h+var_20], rax
0x18011c678  mov     rdi, rcx
0x18011c67b  mov     r14, [rcx+28h]
0x18011c67f  mov     rax, [rcx+38h]
0x18011c683  mov     sil, [rax+170h]
0x18011c68a  lea     rdx, [rcx+48h]
0x18011c68e  lea     rcx, [rbp+57h+var_A0]
0x18011c692  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x18011c697  mov     rbx, rax
0x18011c69a  mov     [rbp+57h+var_28], 0
0x18011c6a2  mov     rcx, [rax+38h]
0x18011c6a6  test    rcx, rcx
0x18011c6a9  jz      short loc_18011C6DA
0x18011c6ab  cmp     rcx, rax
0x18011c6ae  jnz     short loc_18011C6CE
0x18011c6b0  mov     rdx, [rcx]
0x18011c6b3  mov     rax, [rdx+8]
0x18011c6b7  lea     rdx, [rbp+57h+var_60]
0x18011c6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c6c0  mov     [rbp+57h+var_28], rax
0x18011c6c4  mov     rcx, rbx
0x18011c6c7  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c6cc  jmp     short loc_18011C6DA
0x18011c6ce  mov     [rbp+57h+var_28], rcx
0x18011c6d2  mov     qword ptr [rax+38h], 0
0x18011c6da  mov     rcx, rbx
0x18011c6dd  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c6e2  nop
0x18011c6e3  mov     rbx, [rdi+28h]
0x18011c6e7  add     rbx, 160h
0x18011c6ee  mov     [rsp+110h+var_E8], rbx
0x18011c6f3  mov     rcx, rbx
0x18011c6f6  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18011c6fd  nop     dword ptr [rax+rax+00h]
0x18011c702  nop
0x18011c703  mov     [rsp+110h+var_F0], sil
0x18011c708  mov     rcx, [rbp+57h+var_28]
0x18011c70c  test    rcx, rcx
0x18011c70f  jnz     short loc_18011C71E
0x18011c711  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18011c718  nop     dword ptr [rax+rax+00h]
0x18011c71d  int     3; Trap to Debugger
0x18011c71e  mov     rax, [rcx]
0x18011c721  lea     r8, [rsp+110h+var_F0]
0x18011c726  lea     rdx, [rsp+110h+var_E0]
0x18011c72b  mov     rax, [rax+10h]
0x18011c72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c734  nop
0x18011c735  mov     rcx, rbx
0x18011c738  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18011c73f  nop     dword ptr [rax+rax+00h]
0x18011c744  nop
0x18011c745  movups  xmm0, [rsp+110h+var_E0]
0x18011c74a  movaps  [rbp+57h+var_C0], xmm0
0x18011c74e  mov     eax, [rbp+57h+var_D0]
0x18011c751  mov     [rbp+57h+var_B0], eax
0x18011c754  lea     rdx, [rbp+57h+var_C0]
0x18011c758  mov     rcx, r14; this
0x18011c75b  call    ?_FinalizeAndRunContinuations@?$_Task_impl@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@details@Concurrency@@QEAAXU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Z; Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>)
0x18011c760  nop
0x18011c761  lea     rcx, [rbp+57h+var_60]
0x18011c765  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x18011c76a  mov     rcx, [rbp+57h+var_20]
0x18011c76e  xor     rcx, rsp; StackCookie
0x18011c771  call    __security_check_cookie
0x18011c776  lea     r11, [rsp+110h+var_10]
0x18011c77e  mov     rbx, [r11+28h]
0x18011c782  mov     rsi, [r11+30h]
0x18011c786  mov     rsp, r11
0x18011c789  pop     r14
0x18011c78b  pop     rdi
0x18011c78c  pop     rbp
0x18011c78d  retn
```
