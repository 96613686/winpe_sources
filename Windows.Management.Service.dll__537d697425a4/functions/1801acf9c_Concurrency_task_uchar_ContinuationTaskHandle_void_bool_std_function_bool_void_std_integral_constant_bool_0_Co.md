# Concurrency::task<uchar>::_ContinuationTaskHandle<void,bool,std::function<bool (void)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801acf9c`
- end: `0x1801ad07f`
- name: `?_Continue@?$_ContinuationTaskHandle@X_NV?$function@$$A6A_NXZ@std@@U?$integral_constant@_N$0A@@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801af200`

## callees

- `0x1800dabf0`
- `0x1800fed34`
- `0x18011d5b4`
- `0x1801a7b04`
- `0x1801acf9c`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801ad016`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801ad016`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801ad039`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801ad039`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acffa`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801acffa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,bool,std::function<bool (void)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // rbp
  char v3; // di
  Concurrency::details::_TaskEventLogger *v4; // rsi
  _BYTE *v5; // rcx
  __int64 result; // rax
  _BYTE *v7; // rdx
  _BYTE v8[8]; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v9; // [rsp+28h] [rbp-B0h]
  _BYTE v10[56]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE *v11; // [rsp+68h] [rbp-70h]
  _BYTE v12[104]; // [rsp+70h] [rbp-68h] BYREF

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v3 = *(_BYTE *)(*(_QWORD *)(a1 + 56) + 368LL);
  v9 = std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(
         v12,
         a1 + 72);
  Concurrency::details::_MakeUnitToTFunc<bool>(v10, v9);
  std::_Func_class<bool,std::wstring const &>::_Tidy(v9);
  v4 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  v9 = (__int64)v4;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v4);
  v8[0] = v3;
  v5 = v11;
  if ( !v11 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v5 + 16LL))(v5, v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v4);
  result = Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  if ( v11 )
  {
    v7 = v10;
    LOBYTE(v7) = v11 != v10;
    return (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, v7);
  }
  return result;
}

```

## disassembly

```asm
0x1801acf9c  push    rbx
0x1801acf9e  push    rbp
0x1801acf9f  push    rsi
0x1801acfa0  push    rdi
0x1801acfa1  sub     rsp, 0B8h
0x1801acfa8  mov     rsi, rcx
0x1801acfab  mov     rbp, [rcx+28h]
0x1801acfaf  mov     rax, [rcx+38h]
0x1801acfb3  mov     dil, [rax+170h]
0x1801acfba  lea     rdx, [rcx+48h]
0x1801acfbe  lea     rcx, [rsp+0D8h+var_68]
0x1801acfc3  call    ??0?$function@$$A6A?AU?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@U?$pair@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@_K@2@@Z@std@@QEAA@AEBV01@@Z; std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)>(std::function<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult> (std::pair<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,unsigned __int64>)> const &)
0x1801acfc8  mov     rbx, rax
0x1801acfcb  mov     [rsp+0D8h+var_B0], rax
0x1801acfd0  mov     rdx, rax
0x1801acfd3  lea     rcx, [rsp+0D8h+var_A8]
0x1801acfd8  call    ??$_MakeUnitToTFunc@_N@details@Concurrency@@YA?AV?$function@$$A6A_NE@Z@std@@AEBV?$function@$$A6A_NXZ@3@@Z; Concurrency::details::_MakeUnitToTFunc<bool>(std::function<bool (void)> const &)
0x1801acfdd  nop
0x1801acfde  mov     rcx, rbx
0x1801acfe1  call    ?_Tidy@?$_Func_class@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@IEAAXXZ; std::_Func_class<bool,std::wstring const &>::_Tidy(void)
0x1801acfe6  nop
0x1801acfe7  mov     rsi, [rsi+28h]
0x1801acfeb  add     rsi, 160h
0x1801acff2  mov     [rsp+0D8h+var_B0], rsi
0x1801acff7  mov     rcx, rsi
0x1801acffa  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801ad001  nop     dword ptr [rax+rax+00h]
0x1801ad006  nop
0x1801ad007  mov     [rsp+0D8h+var_B8], dil
0x1801ad00c  mov     rcx, [rsp+0D8h+var_70]
0x1801ad011  test    rcx, rcx
0x1801ad014  jnz     short loc_1801AD023
0x1801ad016  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801ad01d  nop     dword ptr [rax+rax+00h]
0x1801ad022  int     3; Trap to Debugger
0x1801ad023  mov     rax, [rcx]
0x1801ad026  lea     rdx, [rsp+0D8h+var_B8]
0x1801ad02b  mov     rax, [rax+10h]
0x1801ad02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad034  mov     bl, al
0x1801ad036  mov     rcx, rsi
0x1801ad039  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801ad040  nop     dword ptr [rax+rax+00h]
0x1801ad045  nop
0x1801ad046  mov     dl, bl
0x1801ad048  mov     rcx, rbp; this
0x1801ad04b  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801ad050  nop
0x1801ad051  mov     rcx, [rsp+0D8h+var_70]
0x1801ad056  test    rcx, rcx
0x1801ad059  jz      short loc_1801AD072
0x1801ad05b  mov     rax, [rcx]
0x1801ad05e  lea     rdx, [rsp+0D8h+var_A8]
0x1801ad063  cmp     rcx, rdx
0x1801ad066  setnz   dl
0x1801ad069  mov     rax, [rax+20h]
0x1801ad06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad072  add     rsp, 0B8h
0x1801ad079  pop     rdi
0x1801ad07a  pop     rsi
0x1801ad07b  pop     rbp
0x1801ad07c  pop     rbx
0x1801ad07d  retn
```
