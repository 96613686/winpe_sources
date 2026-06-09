# SimpleClassFactoryWithAccessControl<DockingInputManager>::~SimpleClassFactoryWithAccessControl<DockingInputManager>(void)

- ea: `0x1800134fc`
- end: `0x180013515`
- name: `??1?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@UEAA@XZ`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800136e0`

## callees

- `0x1800134dc`

## pseudocode

```c
__int64 __fastcall SimpleClassFactoryWithAccessControl<DockingInputManager>::~SimpleClassFactoryWithAccessControl<DockingInputManager>(
        __int64 a1)
{
  return Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::~SimpleClassFactory<DockingInputManager,0>(a1);
}

```

## disassembly

```asm
0x1800134fc  mov     [rsp+arg_0], rcx
0x180013501  sub     rsp, 28h
0x180013505  mov     rcx, [rsp+28h+arg_0]
0x18001350a  call    ??1?$SimpleClassFactory@VDockingInputManager@@$0A@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::~SimpleClassFactory<DockingInputManager,0>(void)
0x18001350f  nop
0x180013510  add     rsp, 28h
0x180013514  retn
```
