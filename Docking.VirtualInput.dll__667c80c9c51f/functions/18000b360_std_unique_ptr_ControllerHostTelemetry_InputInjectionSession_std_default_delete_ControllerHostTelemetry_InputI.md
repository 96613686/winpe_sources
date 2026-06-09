# std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(void)

- ea: `0x18000b360`
- end: `0x18000b38d`
- name: `??$?0U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@$0A@@?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c6bc`
- `0x1800168ec`

## callees

- `0x18000b2f0`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::unique_ptr<ControllerHostTelemetry::InputInjectionSession>(
        __int64 a1)
{
  unsigned __int8 v2; // [rsp+20h] [rbp-18h]

  std::_Compressed_pair<std::default_delete<Docking::VirtualInput::PtpInputManager>,Docking::VirtualInput::PtpInputManager *,1>::_Compressed_pair<std::default_delete<Docking::VirtualInput::PtpInputManager>,Docking::VirtualInput::PtpInputManager *,1>(
    a1,
    v2);
  return a1;
}

```

## disassembly

```asm
0x18000b360  mov     [rsp+arg_0], rcx
0x18000b365  sub     rsp, 38h
0x18000b369  mov     rax, [rsp+38h+arg_0]
0x18000b36e  mov     [rsp+38h+var_10], rax
0x18000b373  movzx   edx, [rsp+38h+var_18]
0x18000b378  mov     rcx, [rsp+38h+var_10]
0x18000b37d  call    ??$?0$$V@?$_Compressed_pair@U?$default_delete@VPtpInputManager@VirtualInput@Docking@@@std@@PEAVPtpInputManager@VirtualInput@Docking@@$00@std@@QEAA@U_Zero_then_variadic_args_t@1@@Z; std::_Compressed_pair<std::default_delete<Docking::VirtualInput::PtpInputManager>,Docking::VirtualInput::PtpInputManager *,1>::_Compressed_pair<std::default_delete<Docking::VirtualInput::PtpInputManager>,Docking::VirtualInput::PtpInputManager *,1>(std::_Zero_then_variadic_args_t)
0x18000b382  nop
0x18000b383  mov     rax, [rsp+38h+arg_0]
0x18000b388  add     rsp, 38h
0x18000b38c  retn
```
