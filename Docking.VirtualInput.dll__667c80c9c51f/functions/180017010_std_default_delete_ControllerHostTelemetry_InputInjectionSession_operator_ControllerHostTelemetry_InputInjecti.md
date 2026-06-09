# std::default_delete<ControllerHostTelemetry::InputInjectionSession>::operator()(ControllerHostTelemetry::InputInjectionSession *)

- ea: `0x180017010`
- end: `0x180017054`
- name: `??R?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@QEBAXPEAVInputInjectionSession@ControllerHostTelemetry@@@Z`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016c8c`
- `0x180019fb4`

## callees

- `0x180017010`
- `0x1800170a0`

## pseudocode

```c
ControllerHostTelemetry::InputInjectionSession *__fastcall std::default_delete<ControllerHostTelemetry::InputInjectionSession>::operator()(
        __int64 a1,
        ControllerHostTelemetry::InputInjectionSession *a2)
{
  ControllerHostTelemetry::InputInjectionSession *result; // rax

  result = a2;
  if ( a2 )
    return (ControllerHostTelemetry::InputInjectionSession *)ControllerHostTelemetry::InputInjectionSession::`scalar deleting destructor'(
                                                               a2,
                                                               1u);
  return result;
}

```

## disassembly

```asm
0x180017010  mov     [rsp+arg_8], rdx
0x180017015  mov     [rsp+arg_0], rcx
0x18001701a  sub     rsp, 38h
0x18001701e  mov     rax, [rsp+38h+arg_8]
0x180017023  mov     [rsp+38h+var_18], rax
0x180017028  cmp     [rsp+38h+var_18], 0
0x18001702e  jz      short loc_180017046
0x180017030  mov     edx, 1; unsigned int
0x180017035  mov     rcx, [rsp+38h+var_18]; this
0x18001703a  call    ??_GInputInjectionSession@ControllerHostTelemetry@@QEAAPEAXI@Z; ControllerHostTelemetry::InputInjectionSession::`scalar deleting destructor'(uint)
0x18001703f  mov     [rsp+38h+var_10], rax
0x180017044  jmp     short loc_18001704F
0x180017046  mov     [rsp+38h+var_10], 0
0x18001704f  add     rsp, 38h
0x180017053  retn
```
