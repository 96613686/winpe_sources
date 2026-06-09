# std::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>(std::_Zero_then_variadic_args_t,ControllerHostTelemetry::InputInjectionSession * &)

- ea: `0x1800145d0`
- end: `0x180014601`
- name: `??$?0AEAPEAVInputInjectionSession@ControllerHostTelemetry@@@?$_Compressed_pair@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@PEAVInputInjectionSession@ControllerHostTelemetry@@$00@std@@QEAA@U_Zero_then_variadic_args_t@1@AEAPEAVInputInjectionSession@ControllerHostTelemetry@@@Z`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014610`

## callees

- `0x18000b810`

## pseudocode

```c
_QWORD *__fastcall std::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>::_Compressed_pair<std::default_delete<ControllerHostTelemetry::InputInjectionSession>,ControllerHostTelemetry::InputInjectionSession *,1>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  *a1 = *(_QWORD *)Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  return a1;
}

```

## disassembly

```asm
0x1800145d0  mov     [rsp+arg_10], r8
0x1800145d5  mov     [rsp+arg_8], dl
0x1800145d9  mov     [rsp+arg_0], rcx
0x1800145de  sub     rsp, 28h
0x1800145e2  mov     rcx, [rsp+28h+arg_10]
0x1800145e7  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800145ec  mov     rcx, [rsp+28h+arg_0]
0x1800145f1  mov     rax, [rax]
0x1800145f4  mov     [rcx], rax
0x1800145f7  mov     rax, [rsp+28h+arg_0]
0x1800145fc  add     rsp, 28h
0x180014600  retn
```
