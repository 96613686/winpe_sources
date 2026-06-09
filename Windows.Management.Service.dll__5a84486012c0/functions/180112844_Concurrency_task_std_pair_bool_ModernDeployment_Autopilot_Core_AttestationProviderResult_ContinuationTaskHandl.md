# Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>::_ContinuationTaskHandle<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>,void,std::function<void (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)>,Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>>(std::function<uchar (Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>>)> &&,Concurrency::task<std::pair<bool,ModernDeployment::Autopilot::Core::AttestationProviderResult>> &&)

- ea: `0x180112844`
- end: `0x1801128ec`
- name: `??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@Z@std@@V?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@?$_ContinuationTaskHandle@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@XV?$function@$$A6AXV?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@Z@2@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@U?$pair@_NUAttestationProviderResult@Core@Autopilot@ModernDeployment@@@std@@@Concurrency@@@Z@std@@$$QEAV12@@Z`
- size: `168`
- prototype: `char __fastcall(__int64, __int64, __int64 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180118b84`
- `0x18011f5dc`
- `0x18018c6dc`
- `0x18018c94c`
- `0x180194e4c`
- `0x1801a71d0`

## callees

- `0x180077384`
- `0x180112844`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801128a6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801128a6`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801128d3`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801128d3`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011286c`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18011286c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180112844  mov     [rsp+arg_10], rbx
0x180112849  mov     [rsp+arg_18], rsi
0x18011284e  push    rdi
0x18011284f  sub     rsp, 30h
0x180112853  mov     rbx, r8
0x180112856  mov     rdi, rdx
0x180112859  mov     rsi, [rcx+28h]
0x18011285d  add     rsi, 160h
0x180112864  mov     [rsp+38h+arg_0], rsi
0x180112869  mov     rcx, rsi
0x18011286c  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180112872  nop
0x180112873  mov     rax, [rbx]
0x180112876  mov     [rsp+38h+var_18], rax
0x18011287b  mov     rax, [rbx+8]
0x18011287f  mov     [rsp+38h+var_10], rax
0x180112884  mov     qword ptr [rbx], 0
0x18011288b  mov     qword ptr [rbx+8], 0
0x180112893  lea     rax, [rsp+38h+var_18]
0x180112898  mov     [rsp+38h+arg_8], rax
0x18011289d  mov     rcx, [rdi+38h]
0x1801128a1  test    rcx, rcx
0x1801128a4  jnz     short loc_1801128AD
0x1801128a6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801128ac  int     3; Trap to Debugger
0x1801128ad  mov     rax, [rcx]
0x1801128b0  lea     rdx, [rsp+38h+var_18]
0x1801128b5  mov     rax, [rax+10h]
0x1801128b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801128be  mov     bl, al
0x1801128c0  mov     rcx, [rsp+38h+var_10]; this
0x1801128c5  test    rcx, rcx
0x1801128c8  jz      short loc_1801128D0
0x1801128ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801128cf  nop
0x1801128d0  mov     rcx, rsi
0x1801128d3  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801128d9  nop
0x1801128da  mov     al, bl
0x1801128dc  mov     rbx, [rsp+38h+arg_10]
0x1801128e1  mov     rsi, [rsp+38h+arg_18]
0x1801128e6  add     rsp, 30h
0x1801128ea  pop     rdi
0x1801128eb  retn
```
