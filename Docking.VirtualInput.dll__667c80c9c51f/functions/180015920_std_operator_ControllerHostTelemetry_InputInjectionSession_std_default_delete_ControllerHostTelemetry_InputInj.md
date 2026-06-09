# std::operator==<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>> const &,std::nullptr_t)

- ea: `0x180015920`
- end: `0x18001595b`
- name: `??$?8VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@YA_NAEBV?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@0@$$T@Z`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015970`

## callees

- `0x180015920`
- `0x180016ef0`

## pseudocode

```c
_BOOL8 __fastcall std::operator==<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(
        __int64 a1)
{
  return (unsigned __int8)std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::operator bool(a1) == 0;
}

```

## disassembly

```asm
0x180015920  mov     [rsp+arg_8], rdx
0x180015925  mov     [rsp+arg_0], rcx
0x18001592a  sub     rsp, 38h
0x18001592e  mov     rcx, [rsp+38h+arg_0]
0x180015933  call    ??B?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEBA_NXZ; std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::operator bool(void)
0x180015938  movzx   eax, al
0x18001593b  test    eax, eax
0x18001593d  jnz     short loc_180015949
0x18001593f  mov     [rsp+38h+var_18], 1
0x180015947  jmp     short loc_180015951
0x180015949  mov     [rsp+38h+var_18], 0
0x180015951  movzx   eax, byte ptr [rsp+38h+var_18]
0x180015956  add     rsp, 38h
0x18001595a  retn
```
