# std::unique_ptr<ControllerHostTelemetry::InputInjectionSession,std::default_delete<ControllerHostTelemetry::InputInjectionSession>>::reset(ControllerHostTelemetry::InputInjectionSession *)

- ea: `0x180019fb4`
- end: `0x18001a008`
- name: `?reset@?$unique_ptr@VInputInjectionSession@ControllerHostTelemetry@@U?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@@std@@QEAAXPEAVInputInjectionSession@ControllerHostTelemetry@@@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800158c0`
- `0x180016e30`

## callees

- `0x18000b810`
- `0x180014740`
- `0x180017010`
- `0x180019fb4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<ControllerHostTelemetry::InputInjectionSession>::reset(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // [rsp+20h] [rbp-18h]
  __int64 v4; // [rsp+28h] [rbp-10h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  result = std::exchange<Docking::VirtualInput::PtpInputManager *,std::nullptr_t>(a1, &v6);
  v3 = result;
  if ( result )
  {
    v4 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
    return std::default_delete<ControllerHostTelemetry::InputInjectionSession>::operator()(v4, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180019fb4  mov     [rsp+arg_8], rdx
0x180019fb9  mov     [rsp+arg_0], rcx
0x180019fbe  sub     rsp, 38h
0x180019fc2  mov     rax, [rsp+38h+arg_0]
0x180019fc7  lea     rdx, [rsp+38h+arg_8]
0x180019fcc  mov     rcx, rax
0x180019fcf  call    ??$exchange@PEAVPtpInputManager@VirtualInput@Docking@@$$T@std@@YAPEAVPtpInputManager@VirtualInput@Docking@@AEAPEAV123@$$QEA$$T@Z
0x180019fd4  mov     [rsp+38h+var_18], rax
0x180019fd9  cmp     [rsp+38h+var_18], 0
0x180019fdf  jz      short loc_18001A003
0x180019fe1  mov     rax, [rsp+38h+arg_0]
0x180019fe6  mov     rcx, rax
0x180019fe9  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180019fee  mov     [rsp+38h+var_10], rax
0x180019ff3  mov     rdx, [rsp+38h+var_18]
0x180019ff8  mov     rcx, [rsp+38h+var_10]
0x180019ffd  call    ??R?$default_delete@VInputInjectionSession@ControllerHostTelemetry@@@std@@QEBAXPEAVInputInjectionSession@ControllerHostTelemetry@@@Z; std::default_delete<ControllerHostTelemetry::InputInjectionSession>::operator()(ControllerHostTelemetry::InputInjectionSession *)
0x18001a002  nop
0x18001a003  add     rsp, 38h
0x18001a007  retn
```
