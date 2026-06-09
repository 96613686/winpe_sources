# std::unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>>::unique_ptr<Docking::VirtualInput::PtpInputManager,std::default_delete<Docking::VirtualInput::PtpInputManager>>(Docking::VirtualInput::PtpInputManager *)

- ea: `0x180014610`
- end: `0x180014647`
- name: `??$?0U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@$0A@@?$unique_ptr@VPtpInputManager@VirtualInput@Docking@@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@@std@@QEAA@PEAVPtpInputManager@VirtualInput@Docking@@@Z`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001477c`
- `0x18001639c`

## callees

- `0x1800145d0`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Docking::VirtualInput::PtpInputManager>::unique_ptr<Docking::VirtualInput::PtpInputManager>(
        __int64 a1,
        __int64 a2)
{
  unsigned __int8 v3; // [rsp+20h] [rbp-18h]
  __int64 v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  std::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>(
    a1,
    v3,
    &v5);
  return a1;
}

```

## disassembly

```asm
0x180014610  mov     [rsp+arg_8], rdx
0x180014615  mov     [rsp+arg_0], rcx
0x18001461a  sub     rsp, 38h
0x18001461e  mov     rax, [rsp+38h+arg_0]
0x180014623  mov     [rsp+38h+var_10], rax
0x180014628  lea     r8, [rsp+38h+arg_8]
0x18001462d  movzx   edx, [rsp+38h+var_18]
0x180014632  mov     rcx, [rsp+38h+var_10]
0x180014637  call    ??$?0AEAPEAVInputInjectionSession@ControllerHostTelemetry@@@?$_Compressed_pair@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@PEAVInputInjectionSession@ControllerHostTelemetry@@$00@std@@QEAA@U_Zero_then_variadic_args_t@1@AEAPEAVInputInjectionSession@ControllerHostTelemetry@@@Z; std::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>(std::_Zero_then_variadic_args_t,ControllerHostTelemetry::InputInjectionSession * &)
0x18001463c  nop
0x18001463d  mov     rax, [rsp+38h+arg_0]
0x180014642  add     rsp, 38h
0x180014646  retn
```
