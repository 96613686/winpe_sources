# Concurrency::task<bool>::_ContinuationTaskHandle<bool,std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (bool)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x180118d88`
- end: `0x180118eb4`
- name: `?_Continue@?$_ContinuationTaskHandle@_NU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@V?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_N@Z@2@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@_N@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011b110`

## callees

- `0x18000b820`
- `0x1800d84e0`
- `0x1800fbc44`
- `0x180118d88`
- `0x180119e68`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180118e43`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180118e43`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118e64`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118e64`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118e2e`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180118e2e`

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
  _BYTE v9[8]; // [rsp+20h] [rbp-99h] BYREF
  Concurrency::details::_TaskEventLogger *v10; // [rsp+28h] [rbp-91h]
  __int128 v11; // [rsp+30h] [rbp-89h] BYREF
  int v12; // [rsp+40h] [rbp-79h]
  __int128 v13; // [rsp+50h] [rbp-69h]
  int v14; // [rsp+60h] [rbp-59h]
  _BYTE v15[64]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v16[56]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+E8h] [rbp+2Fh]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_BYTE *)(*(_QWORD *)(a1 + 56) + 368LL);
  v4 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v15,
         a1 + 72);
  v5 = v4;
  v17 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  if ( v6 )
  {
    if ( v6 == v4 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v6 + 8LL))(v6, v16);
      std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
    }
    else
    {
      v17 = *(_QWORD *)(v4 + 56);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  std::_Func_class<bool,std::wstring const &>::_Tidy(v5);
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  v10 = v7;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v9[0] = v3;
  if ( !v17 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, __int128 *, _BYTE *))(*(_QWORD *)v17 + 16LL))(v17, &v11, v9);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  v13 = v11;
  v14 = v12;
  Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(v2);
  return std::_Func_class<bool,std::wstring const &>::_Tidy(v16);
}

```

## disassembly

```asm
0x180118d88  mov     [rsp-8+arg_8], rbx
0x180118d8d  mov     [rsp-8+arg_10], rsi
0x180118d92  push    rbp
0x180118d93  push    rdi
0x180118d94  push    r14
0x180118d96  lea     rbp, [rsp-47h]
0x180118d9b  sub     rsp, 100h
0x180118da2  mov     rax, cs:__security_cookie
0x180118da9  xor     rax, rsp
0x180118dac  mov     [rbp+57h+var_20], rax
0x180118db0  mov     rdi, rcx
0x180118db3  mov     r14, [rcx+28h]
0x180118db7  mov     rax, [rcx+38h]
0x180118dbb  mov     sil, [rax+170h]
0x180118dc2  lea     rdx, [rcx+48h]
0x180118dc6  lea     rcx, [rbp+57h+var_A0]
0x180118dca  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x180118dcf  mov     rbx, rax
0x180118dd2  mov     [rbp+57h+var_28], 0
0x180118dda  mov     rcx, [rax+38h]
0x180118dde  test    rcx, rcx
0x180118de1  jz      short loc_180118E12
0x180118de3  cmp     rcx, rax
0x180118de6  jnz     short loc_180118E06
0x180118de8  mov     rdx, [rcx]
0x180118deb  mov     rax, [rdx+8]
0x180118def  lea     rdx, [rbp+57h+var_60]
0x180118df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118df8  mov     [rbp+57h+var_28], rax
0x180118dfc  mov     rcx, rbx
0x180118dff  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118e04  jmp     short loc_180118E12
0x180118e06  mov     [rbp+57h+var_28], rcx
0x180118e0a  mov     qword ptr [rax+38h], 0
0x180118e12  mov     rcx, rbx
0x180118e15  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118e1a  nop
0x180118e1b  mov     rbx, [rdi+28h]
0x180118e1f  add     rbx, 160h
0x180118e26  mov     [rsp+110h+var_E8], rbx
0x180118e2b  mov     rcx, rbx
0x180118e2e  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180118e34  nop
0x180118e35  mov     [rsp+110h+var_F0], sil
0x180118e3a  mov     rcx, [rbp+57h+var_28]
0x180118e3e  test    rcx, rcx
0x180118e41  jnz     short loc_180118E4A
0x180118e43  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180118e49  int     3; Trap to Debugger
0x180118e4a  mov     rax, [rcx]
0x180118e4d  lea     r8, [rsp+110h+var_F0]
0x180118e52  lea     rdx, [rsp+110h+var_E0]
0x180118e57  mov     rax, [rax+10h]
0x180118e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118e60  nop
0x180118e61  mov     rcx, rbx
0x180118e64  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180118e6a  nop
0x180118e6b  movups  xmm0, [rsp+110h+var_E0]
0x180118e70  movaps  [rbp+57h+var_C0], xmm0
0x180118e74  mov     eax, [rbp+57h+var_D0]
0x180118e77  mov     [rbp+57h+var_B0], eax
0x180118e7a  lea     rdx, [rbp+57h+var_C0]
0x180118e7e  mov     rcx, r14; this
0x180118e81  call    ?_FinalizeAndRunContinuations@?$_Task_impl@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@details@Concurrency@@QEAAXU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Z; Concurrency::details::_Task_impl<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_FinalizeAndRunContinuations(std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>)
0x180118e86  nop
0x180118e87  lea     rcx, [rbp+57h+var_60]
0x180118e8b  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x180118e90  mov     rcx, [rbp+57h+var_20]
0x180118e94  xor     rcx, rsp; StackCookie
0x180118e97  call    __security_check_cookie
0x180118e9c  lea     r11, [rsp+110h+var_10]
0x180118ea4  mov     rbx, [r11+28h]
0x180118ea8  mov     rsi, [r11+30h]
0x180118eac  mov     rsp, r11
0x180118eaf  pop     r14
0x180118eb1  pop     rdi
0x180118eb2  pop     rbp
0x180118eb3  retn
```
