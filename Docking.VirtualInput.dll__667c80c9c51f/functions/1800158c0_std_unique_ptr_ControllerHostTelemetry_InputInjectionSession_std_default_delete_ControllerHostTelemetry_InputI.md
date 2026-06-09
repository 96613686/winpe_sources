# std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>::operator=<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,0>(std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>> &&)

- ea: `0x1800158c0`
- end: `0x180015911`
- name: `??$?4U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@$0A@@?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800174bc`

## callees

- `0x18000b810`
- `0x180015348`
- `0x180019fb4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::operator=<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,0>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rax

  v2 = std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::release(a2);
  std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::reset(a1, v2);
  v3 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a2);
  Microsoft::WRL::Details::Forward<std::nullptr_t>(v3);
  Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
  return a1;
}

```

## disassembly

```asm
0x1800158c0  mov     [rsp+arg_8], rdx
0x1800158c5  mov     [rsp+arg_0], rcx
0x1800158ca  sub     rsp, 28h
0x1800158ce  mov     rcx, [rsp+28h+arg_8]
0x1800158d3  call    ?release@?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAAPEAVInputInjectionSession@ControllerHostTelemetry@@XZ; std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::release(void)
0x1800158d8  mov     rdx, rax
0x1800158db  mov     rcx, [rsp+28h+arg_0]
0x1800158e0  call    ?reset@?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAAXPEAVInputInjectionSession@ControllerHostTelemetry@@@Z; std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::reset(ControllerHostTelemetry::InputInjectionSession *)
0x1800158e5  mov     rax, [rsp+28h+arg_8]
0x1800158ea  mov     rcx, rax
0x1800158ed  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800158f2  mov     rcx, rax
0x1800158f5  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800158fa  mov     rax, [rsp+28h+arg_0]
0x1800158ff  mov     rcx, rax
0x180015902  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180015907  mov     rax, [rsp+28h+arg_0]
0x18001590c  add     rsp, 28h
0x180015910  retn
```
