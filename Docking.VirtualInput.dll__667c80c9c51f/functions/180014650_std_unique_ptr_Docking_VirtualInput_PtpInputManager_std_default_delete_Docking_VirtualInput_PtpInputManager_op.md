# std::unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>>::operator=<std::default_delete<Docking::VirtualInput::PtpInputManager>,0>(std::unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>> &&)

- ea: `0x180014650`
- end: `0x1800146a1`
- name: `??$?4U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@$0A@@?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014d08`

## callees

- `0x18000b810`
- `0x180015348`
- `0x180015378`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Docking::VirtualInput::PtpInputManager>::operator=<std::default_delete<Docking::VirtualInput::PtpInputManager>,0>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rax

  v2 = std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::release(a2);
  std::unique_ptr<Docking::VirtualInput::PtpInputManager>::reset(a1, v2);
  v3 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a2);
  Microsoft::WRL::Details::Forward<std::nullptr_t>(v3);
  Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
  return a1;
}

```

## disassembly

```asm
0x180014650  mov     [rsp+arg_8], rdx
0x180014655  mov     [rsp+arg_0], rcx
0x18001465a  sub     rsp, 28h
0x18001465e  mov     rcx, [rsp+28h+arg_8]
0x180014663  call    ?release@?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAAPEAVInputInjectionSession@ControllerHostTelemetry@@XZ; std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::release(void)
0x180014668  mov     rdx, rax
0x18001466b  mov     rcx, [rsp+28h+arg_0]
0x180014670  call    ?reset@?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAAXPEAVPtpInputManager@VirtualInput@Docking@@@Z; std::unique_ptr<Docking::VirtualInput::PtpInputManager>::reset(Docking::VirtualInput::PtpInputManager *)
0x180014675  mov     rax, [rsp+28h+arg_8]
0x18001467a  mov     rcx, rax
0x18001467d  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180014682  mov     rcx, rax
0x180014685  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001468a  mov     rax, [rsp+28h+arg_0]
0x18001468f  mov     rcx, rax
0x180014692  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180014697  mov     rax, [rsp+28h+arg_0]
0x18001469c  add     rsp, 28h
0x1800146a0  retn
```
