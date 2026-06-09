# SimpleClassFactoryWithAccessControl<DockingInputManager>::SimpleClassFactoryWithAccessControl<DockingInputManager>(void)

- ea: `0x1800133b8`
- end: `0x1800133e4`
- name: `??0?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012f94`

## callees

- `0x180013384`

## pseudocode

```c
_QWORD *__fastcall SimpleClassFactoryWithAccessControl<DockingInputManager>::SimpleClassFactoryWithAccessControl<DockingInputManager>(
        _QWORD *a1)
{
  Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::SimpleClassFactory<DockingInputManager,0>(a1);
  *a1 = &SimpleClassFactoryWithAccessControl<DockingInputManager>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x1800133b8  mov     [rsp+arg_0], rcx
0x1800133bd  sub     rsp, 28h
0x1800133c1  mov     rcx, [rsp+28h+arg_0]
0x1800133c6  call    ??0?$SimpleClassFactory@VDockingInputManager@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<DockingInputManager,0>::SimpleClassFactory<DockingInputManager,0>(void)
0x1800133cb  mov     rax, [rsp+28h+arg_0]
0x1800133d0  lea     rcx, ??_7?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@6B@; const SimpleClassFactoryWithAccessControl<DockingInputManager>::`vftable'
0x1800133d7  mov     [rax], rcx
0x1800133da  mov     rax, [rsp+28h+arg_0]
0x1800133df  add     rsp, 28h
0x1800133e3  retn
```
