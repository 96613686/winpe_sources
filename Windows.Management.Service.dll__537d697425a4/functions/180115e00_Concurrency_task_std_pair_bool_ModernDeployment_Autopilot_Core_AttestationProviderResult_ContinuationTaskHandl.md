# Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_ContinuationTaskHandle<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,void,std::function<void (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)>,Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>>(std::function<uchar (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)> &&,Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>> &&)

- ea: `0x180115e00`
- end: `0x180115ebb`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@Z@std@@V?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@?$_ContinuationTaskHandle@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@XV?$function@$$A6AXV?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@Z@2@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@Z@std@@$$QEAV12@@Z`
- size: `187`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011c438`
- `0x1801230d0`
- `0x18019150c`
- `0x180191788`
- `0x180199f08`
- `0x1801aca60`

## callees

- `0x180077c04`
- `0x180115e00`
- `0x180200010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180115e68`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180115e68`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180115e9b`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180115e9b`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180115e28`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180115e28`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_ContinuationTaskHandle<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,void,std::function<void (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<unsigned char (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)>,Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  Concurrency::details::_TaskEventLogger *v5; // rsi
  __int64 v6; // rcx
  char v7; // bl
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-10h]

  v5 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v5);
  v9 = *a3;
  v10 = (std::_Ref_count_base *)a3[1];
  *a3 = 0;
  a3[1] = 0;
  v6 = *(_QWORD *)(a2 + 56);
  if ( !v6 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, &v9);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v5);
  return v7;
}

```

## disassembly

```asm
0x180115e00  mov     [rsp+arg_10], rbx
0x180115e05  mov     [rsp+arg_18], rsi
0x180115e0a  push    rdi
0x180115e0b  sub     rsp, 30h
0x180115e0f  mov     rbx, r8
0x180115e12  mov     rdi, rdx
0x180115e15  mov     rsi, [rcx+28h]
0x180115e19  add     rsi, 160h
0x180115e20  mov     [rsp+38h+arg_0], rsi
0x180115e25  mov     rcx, rsi
0x180115e28  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180115e2f  nop     dword ptr [rax+rax+00h]
0x180115e34  nop
0x180115e35  mov     rax, [rbx]
0x180115e38  mov     [rsp+38h+var_18], rax
0x180115e3d  mov     rax, [rbx+8]
0x180115e41  mov     [rsp+38h+var_10], rax
0x180115e46  mov     qword ptr [rbx], 0
0x180115e4d  mov     qword ptr [rbx+8], 0
0x180115e55  lea     rax, [rsp+38h+var_18]
0x180115e5a  mov     [rsp+38h+arg_8], rax
0x180115e5f  mov     rcx, [rdi+38h]
0x180115e63  test    rcx, rcx
0x180115e66  jnz     short loc_180115E75
0x180115e68  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180115e6f  nop     dword ptr [rax+rax+00h]
0x180115e74  int     3; Trap to Debugger
0x180115e75  mov     rax, [rcx]
0x180115e78  lea     rdx, [rsp+38h+var_18]
0x180115e7d  mov     rax, [rax+10h]
0x180115e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115e86  mov     bl, al
0x180115e88  mov     rcx, [rsp+38h+var_10]; this
0x180115e8d  test    rcx, rcx
0x180115e90  jz      short loc_180115E98
0x180115e92  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180115e97  nop
0x180115e98  mov     rcx, rsi
0x180115e9b  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180115ea2  nop     dword ptr [rax+rax+00h]
0x180115ea7  nop
0x180115ea8  mov     al, bl
0x180115eaa  mov     rbx, [rsp+38h+arg_10]
0x180115eaf  mov     rsi, [rsp+38h+arg_18]
0x180115eb4  add     rsp, 30h
0x180115eb8  pop     rdi
0x180115eb9  retn
```
