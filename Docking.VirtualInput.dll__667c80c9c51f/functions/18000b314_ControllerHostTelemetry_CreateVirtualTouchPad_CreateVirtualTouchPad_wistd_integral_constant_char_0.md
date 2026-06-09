# ControllerHostTelemetry::CreateVirtualTouchPad::CreateVirtualTouchPad(wistd::integral_constant<char,0>)

- ea: `0x18000b314`
- end: `0x18000b359`
- name: `??$?0$$V@CreateVirtualTouchPad@ControllerHostTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd40`

## callees

- `0x18000be08`
- `0x18001139c`

## string_xrefs

- `0x18000b324`: `CreateVirtualTouchPad`

## pseudocode

```c
ControllerHostTelemetry::CreateVirtualTouchPad *__fastcall ControllerHostTelemetry::CreateVirtualTouchPad::CreateVirtualTouchPad(
        ControllerHostTelemetry::CreateVirtualTouchPad *a1)
{
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    "CreateVirtualTouchPad",
    0);
  *(_QWORD *)a1 = &ControllerHostTelemetry::CreateVirtualTouchPad::`vftable';
  ControllerHostTelemetry::CreateVirtualTouchPad::StartActivity(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b314  mov     [rsp+arg_8], dl
0x18000b318  mov     [rsp+arg_0], rcx
0x18000b31d  sub     rsp, 28h
0x18000b321  xor     r8d, r8d
0x18000b324  lea     rdx, aCreatevirtualt_0; "CreateVirtualTouchPad"
0x18000b32b  mov     rcx, [rsp+28h+arg_0]
0x18000b330  call    ??0?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000b335  mov     rax, [rsp+28h+arg_0]
0x18000b33a  lea     rcx, ??_7CreateVirtualTouchPad@ControllerHostTelemetry@@6B@; const ControllerHostTelemetry::CreateVirtualTouchPad::`vftable'
0x18000b341  mov     [rax], rcx
0x18000b344  mov     rcx, [rsp+28h+arg_0]; this
0x18000b349  call    ?StartActivity@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXXZ; ControllerHostTelemetry::CreateVirtualTouchPad::StartActivity(void)
0x18000b34e  nop
0x18000b34f  mov     rax, [rsp+28h+arg_0]
0x18000b354  add     rsp, 28h
0x18000b358  retn
```
