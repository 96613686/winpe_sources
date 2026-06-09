# Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::CopyTo(SimpleClassFactoryWithAccessControl<DockingInputManager> * *)

- ea: `0x18000d8ec`
- end: `0x18000d91b`
- name: `?CopyTo@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAJPEAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Z`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bb28`
- `0x180012f94`

## callees

- `0x18000ebb0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::CopyTo(
        _QWORD *a1,
        _QWORD *a2)
{
  Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::InternalAddRef(a1);
  *a2 = *a1;
  return 0;
}

```

## disassembly

```asm
0x18000d8ec  mov     [rsp+arg_8], rdx
0x18000d8f1  mov     [rsp+arg_0], rcx
0x18000d8f6  sub     rsp, 28h
0x18000d8fa  mov     rcx, [rsp+28h+arg_0]
0x18000d8ff  call    ?InternalAddRef@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::InternalAddRef(void)
0x18000d904  mov     rax, [rsp+28h+arg_8]
0x18000d909  mov     rcx, [rsp+28h+arg_0]
0x18000d90e  mov     rcx, [rcx]
0x18000d911  mov     [rax], rcx
0x18000d914  xor     eax, eax
0x18000d916  add     rsp, 28h
0x18000d91a  retn
```
