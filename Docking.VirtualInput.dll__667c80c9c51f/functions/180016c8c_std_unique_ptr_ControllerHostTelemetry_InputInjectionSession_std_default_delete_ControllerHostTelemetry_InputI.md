# std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>::~unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>(void)

- ea: `0x180016c8c`
- end: `0x180016cd4`
- name: `??1?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAA@XZ`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016d38`
- `0x1800174bc`

## callees

- `0x18000b810`
- `0x180016c8c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::~unique_ptr<ControllerHostTelemetry::InputInjectionSession>(
        _QWORD *a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+28h] [rbp-10h]

  result = (__int64)a1;
  if ( *a1 )
  {
    v2 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
    return std::default_delete<ControllerHostTelemetry::InputInjectionSession>::operator()(v2, *a1);
  }
  return result;
}

```

## disassembly

```asm
0x180016c8c  mov     [rsp+arg_0], rcx
0x180016c91  sub     rsp, 38h
0x180016c95  mov     rax, [rsp+38h+arg_0]
0x180016c9a  cmp     qword ptr [rax], 0
0x180016c9e  jz      short loc_180016CCF
0x180016ca0  mov     rax, [rsp+38h+arg_0]
0x180016ca5  mov     rcx, rax
0x180016ca8  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180016cad  mov     [rsp+38h+var_10], rax
0x180016cb2  mov     rax, [rsp+38h+arg_0]
0x180016cb7  mov     rax, [rax]
0x180016cba  mov     [rsp+38h+var_18], rax
0x180016cbf  mov     rdx, [rsp+38h+var_18]
0x180016cc4  mov     rcx, [rsp+38h+var_10]
0x180016cc9  call    ??R?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@QEBAXPEAVInputInjectionSession@ControllerHostTelemetry@@@Z; std::default_delete<ControllerHostTelemetry::InputInjectionSession>::operator()(ControllerHostTelemetry::InputInjectionSession *)
0x180016cce  nop
0x180016ccf  add     rsp, 38h
0x180016cd3  retn
```
