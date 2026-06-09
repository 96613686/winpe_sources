# ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad(void)

- ea: `0x18000cb70`
- end: `0x18000cba3`
- name: `??1CreateVirtualTouchPad@ControllerHostTelemetry@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(ControllerHostTelemetry::CreateVirtualTouchPad *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012960`

## callees

- `0x18000c7a0`
- `0x18000da00`

## pseudocode

```c
void __fastcall ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad(
        ControllerHostTelemetry::CreateVirtualTouchPad *this)
{
  *(_QWORD *)this = &ControllerHostTelemetry::CreateVirtualTouchPad::`vftable';
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x18000cb70  mov     [rsp+arg_0], rcx
0x18000cb75  sub     rsp, 28h
0x18000cb79  mov     rax, [rsp+28h+arg_0]
0x18000cb7e  lea     rcx, ??_7CreateVirtualTouchPad@ControllerHostTelemetry@@6B@; const ControllerHostTelemetry::CreateVirtualTouchPad::`vftable'
0x18000cb85  mov     [rax], rcx
0x18000cb88  mov     rcx, [rsp+28h+arg_0]
0x18000cb8d  call    ?Destroy@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000cb92  nop
0x18000cb93  mov     rcx, [rsp+28h+arg_0]
0x18000cb98  call    ??1?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000cb9d  nop
0x18000cb9e  add     rsp, 28h
0x18000cba2  retn
```
