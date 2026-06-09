# Concurrency::task<bool>::_ContinuationTaskHandle<bool,void,std::function<void (Concurrency::task<bool>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1801a7a2c`
- end: `0x1801a7b7a`
- name: `?_Continue@?$_ContinuationTaskHandle@_NXV?$function@$$A6AXV?$task@_N@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@_N@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801a9360`

## callees

- `0x180077384`
- `0x180093a28`
- `0x180114024`
- `0x180114090`
- `0x180119d1c`
- `0x18011b4a8`
- `0x1801a24d8`
- `0x1801a7a2c`
- `0x1801fa010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a7af6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a7af6`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a7b21`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a7b21`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a7ad2`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1801a7ad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Concurrency::task<bool>::_ContinuationTaskHandle<bool,void,std::function<void (Concurrency::task<bool>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  __int64 v2; // rax
  Concurrency::details::_Task_impl_base *v3; // r14
  __int64 updated; // rbx
  __int64 *v5; // rcx
  __int64 v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdi
  std::_Ref_count_base *v10; // rcx
  _BYTE *v11; // rdx
  __int64 v12; // [rsp+28h] [rbp-71h] BYREF
  std::_Ref_count_base *v13; // [rsp+30h] [rbp-69h]
  std::_Ref_count_base *v14[2]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v15[24]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v16[56]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE *v17; // [rsp+98h] [rbp-1h]
  _BYTE v18[64]; // [rsp+A0h] [rbp+7h] BYREF

  *(_OWORD *)v14 = 0;
  v2 = std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
         &v12,
         a1 + 56);
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::swap(v2, v14);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v3 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  updated = std::function<void (Concurrency::task<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateInstallResult>>)>::function<void (Concurrency::task<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateInstallResult>>)>(
              v18,
              a1 + 72);
  Concurrency::details::_MakeTToUnitFunc<Concurrency::task<bool>>((__int64)v16, updated);
  v5 = *(__int64 **)(updated + 56);
  if ( v5 )
  {
    v6 = *v5;
    LOBYTE(v6) = v5 != (__int64 *)updated;
    (*(void (__fastcall **)(__int64 *, __int64))(*v5 + 32))(v5, v6);
    *(_QWORD *)(updated + 56) = 0;
  }
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v8 = Concurrency::task<bool>::task<bool>(v15, v14);
  v9 = v8;
  v12 = v8;
  if ( !v17 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v17 + 16LL))(v17, v8);
  v10 = *(std::_Ref_count_base **)(v9 + 8);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v3);
  if ( v17 )
  {
    v11 = v16;
    LOBYTE(v11) = v17 != v16;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, v11);
  }
  if ( v14[1] )
    std::_Ref_count_base::_Decref(v14[1]);
}

```

## disassembly

```asm
0x1801a7a2c  mov     [rsp-8+arg_8], rbx
0x1801a7a31  mov     [rsp-8+arg_10], rsi
0x1801a7a36  push    rbp
0x1801a7a37  push    rdi
0x1801a7a38  push    r14
0x1801a7a3a  lea     rbp, [rsp-47h]
0x1801a7a3f  sub     rsp, 0E0h
0x1801a7a46  mov     rdi, rcx
0x1801a7a49  xorps   xmm0, xmm0
0x1801a7a4c  movdqu  xmmword ptr [rbp+57h+var_B8], xmm0
0x1801a7a51  lea     rdx, [rcx+38h]
0x1801a7a55  lea     rcx, [rbp+57h+var_C8]
0x1801a7a59  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x1801a7a5e  lea     rdx, [rbp+57h+var_B8]
0x1801a7a62  mov     rcx, rax
0x1801a7a65  call    ?swap@?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::swap(std::shared_ptr<Concurrency::details::_ExceptionHolder> &)
0x1801a7a6a  mov     rcx, [rbp+57h+var_C0]; this
0x1801a7a6e  test    rcx, rcx
0x1801a7a71  jz      short loc_1801A7A78
0x1801a7a73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a7a78  mov     r14, [rdi+28h]
0x1801a7a7c  lea     rdx, [rdi+48h]
0x1801a7a80  lea     rcx, [rbp+57h+var_50]
0x1801a7a84  call    ??0?$function@$$A6AXV?$task@V?$shared_ptr@VIAutopilotUpdateInstallResult@Autopilot@Windows@Microsoft@@@std@@@Concurrency@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (Concurrency::task<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateInstallResult>>)>::function<void (Concurrency::task<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateInstallResult>>)>(std::function<void (Concurrency::task<std::shared_ptr<Microsoft::Windows::Autopilot::IAutopilotUpdateInstallResult>>)> const &)
0x1801a7a89  mov     rbx, rax
0x1801a7a8c  mov     [rbp+57h+var_D0], rax
0x1801a7a90  mov     rdx, rax
0x1801a7a93  lea     rcx, [rbp+57h+var_90]
0x1801a7a97  call    ??$_MakeTToUnitFunc@V?$task@_N@Concurrency@@@details@Concurrency@@YA?AV?$function@$$A6AEV?$task@_N@Concurrency@@@Z@std@@AEBV?$function@$$A6AXV?$task@_N@Concurrency@@@Z@3@@Z; Concurrency::details::_MakeTToUnitFunc<Concurrency::task<bool>>(std::function<void (Concurrency::task<bool>)> const &)
0x1801a7a9c  nop
0x1801a7a9d  mov     rcx, [rbx+38h]
0x1801a7aa1  test    rcx, rcx
0x1801a7aa4  jz      short loc_1801A7AC0
0x1801a7aa6  mov     rdx, [rcx]
0x1801a7aa9  mov     rax, [rdx+20h]
0x1801a7aad  cmp     rcx, rbx
0x1801a7ab0  setnz   dl
0x1801a7ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7ab8  mov     qword ptr [rbx+38h], 0
0x1801a7ac0  mov     rbx, [rdi+28h]
0x1801a7ac4  add     rbx, 160h
0x1801a7acb  mov     [rbp+57h+var_D0], rbx
0x1801a7acf  mov     rcx, rbx
0x1801a7ad2  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1801a7ad8  nop
0x1801a7ad9  lea     rdx, [rbp+57h+var_B8]
0x1801a7add  lea     rcx, [rbp+57h+var_A8]
0x1801a7ae1  call    ??0?$task@_N@Concurrency@@QEAA@$$QEAV01@@Z; Concurrency::task<bool>::task<bool>(Concurrency::task<bool> &&)
0x1801a7ae6  mov     rdi, rax
0x1801a7ae9  mov     [rbp+57h+var_C8], rax
0x1801a7aed  mov     rcx, [rbp+57h+var_58]
0x1801a7af1  test    rcx, rcx
0x1801a7af4  jnz     short loc_1801A7AFD
0x1801a7af6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1801a7afc  int     3; Trap to Debugger
0x1801a7afd  mov     rax, [rcx]
0x1801a7b00  mov     rdx, rdi
0x1801a7b03  mov     rax, [rax+10h]
0x1801a7b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7b0c  mov     sil, al
0x1801a7b0f  mov     rcx, [rdi+8]; this
0x1801a7b13  test    rcx, rcx
0x1801a7b16  jz      short loc_1801A7B1E
0x1801a7b18  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a7b1d  nop
0x1801a7b1e  mov     rcx, rbx
0x1801a7b21  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1801a7b27  nop
0x1801a7b28  mov     dl, sil
0x1801a7b2b  mov     rcx, r14; this
0x1801a7b2e  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1801a7b33  nop
0x1801a7b34  mov     rcx, [rbp+57h+var_58]
0x1801a7b38  test    rcx, rcx
0x1801a7b3b  jz      short loc_1801A7B54
0x1801a7b3d  mov     rax, [rcx]
0x1801a7b40  lea     rdx, [rbp+57h+var_90]
0x1801a7b44  cmp     rcx, rdx
0x1801a7b47  setnz   dl
0x1801a7b4a  mov     rax, [rax+20h]
0x1801a7b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a7b53  nop
0x1801a7b54  mov     rcx, [rbp+57h+var_B8+8]; this
0x1801a7b58  test    rcx, rcx
0x1801a7b5b  jz      short loc_1801A7B62
0x1801a7b5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a7b62  lea     r11, [rsp+0F0h+var_10]
0x1801a7b6a  mov     rbx, [r11+28h]
0x1801a7b6e  mov     rsi, [r11+30h]
0x1801a7b72  mov     rsp, r11
0x1801a7b75  pop     r14
0x1801a7b77  pop     rdi
0x1801a7b78  pop     rbp
0x1801a7b79  retn
```
