# Microsoft::WRL::ComPtr<IMarshal>::operator int Microsoft::WRL::Details::BoolStruct::*(void)

- ea: `0x18000cd08`
- end: `0x18000cd3b`
- name: `??B?$ComPtr@UIMarshal@@@WRL@Microsoft@@QEBAPEQBoolStruct@Details@12@HXZ`
- size: `51`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc70`
- `0x18000e2c0`
- `0x18000e610`
- `0x18000f270`
- `0x180010900`
- `0x180012430`

## callees

- `0x18000cd08`
- `0x18000cdc0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IMarshal>::operator int Microsoft::WRL::Details::BoolStruct::*(__int64 a1)
{
  if ( Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(a1) )
    return 0;
  else
    return (unsigned int)-1;
}

```

## disassembly

```asm
0x18000cd08  mov     [rsp+arg_0], rcx
0x18000cd0d  sub     rsp, 38h
0x18000cd11  mov     rcx, [rsp+38h+arg_0]
0x18000cd16  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x18000cd1b  test    rax, rax
0x18000cd1e  jz      short loc_18000CD2A
0x18000cd20  mov     [rsp+38h+var_18], 0
0x18000cd28  jmp     short loc_18000CD32
0x18000cd2a  mov     [rsp+38h+var_18], 0FFFFFFFFh
0x18000cd32  mov     eax, [rsp+38h+var_18]
0x18000cd36  add     rsp, 38h
0x18000cd3a  retn
```
