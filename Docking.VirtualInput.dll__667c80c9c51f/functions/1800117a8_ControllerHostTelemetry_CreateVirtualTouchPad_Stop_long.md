# ControllerHostTelemetry::CreateVirtualTouchPad::Stop(long)

- ea: `0x1800117a8`
- end: `0x1800117c9`
- name: `?Stop@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXJ@Z`
- size: `33`
- prototype: `void __fastcall(ControllerHostTelemetry::CreateVirtualTouchPad *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012960`
- `0x1800174bc`

## callees

- `0x1800115ac`

## pseudocode

```c
void __fastcall ControllerHostTelemetry::CreateVirtualTouchPad::Stop(
        ControllerHostTelemetry::CreateVirtualTouchPad *this,
        unsigned int a2)
{
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    (__int64)this,
    a2);
}

```

## disassembly

```asm
0x1800117a8  mov     [rsp+arg_8], edx
0x1800117ac  mov     [rsp+arg_0], rcx
0x1800117b1  sub     rsp, 28h
0x1800117b5  mov     edx, [rsp+28h+arg_8]
0x1800117b9  mov     rcx, [rsp+28h+arg_0]
0x1800117be  call    ?Stop@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800117c3  nop
0x1800117c4  add     rsp, 28h
0x1800117c8  retn
```
