# std::operator!=<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>> const &,std::nullptr_t)

- ea: `0x180015970`
- end: `0x1800159ad`
- name: `??$?9VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@YA_NAEBV?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@0@$$T@Z`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800174bc`

## callees

- `0x180015920`
- `0x180015970`

## pseudocode

```c
_BOOL8 __fastcall std::operator!=<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(
        __int64 a1)
{
  return !std::operator==<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(a1);
}

```

## disassembly

```asm
0x180015970  mov     [rsp+arg_8], rdx
0x180015975  mov     [rsp+arg_0], rcx
0x18001597a  sub     rsp, 38h
0x18001597e  xor     edx, edx
0x180015980  mov     rcx, [rsp+38h+arg_0]
0x180015985  call    ??$?8VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@YA_NAEBV?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@0@$$T@Z; std::operator==<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(std::unique_ptr<ControllerHostTelemetry::InputInjectionSession> const &,std::nullptr_t)
0x18001598a  movzx   eax, al
0x18001598d  test    eax, eax
0x18001598f  jnz     short loc_18001599B
0x180015991  mov     [rsp+38h+var_18], 1
0x180015999  jmp     short loc_1800159A3
0x18001599b  mov     [rsp+38h+var_18], 0
0x1800159a3  movzx   eax, byte ptr [rsp+38h+var_18]
0x1800159a8  add     rsp, 38h
0x1800159ac  retn
```
