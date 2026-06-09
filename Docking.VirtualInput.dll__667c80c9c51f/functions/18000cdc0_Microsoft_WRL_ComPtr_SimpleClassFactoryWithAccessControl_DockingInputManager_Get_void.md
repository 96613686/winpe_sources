# Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)

- ea: `0x18000cdc0`
- end: `0x18000cdce`
- name: `?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ`
- size: `14`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b394`
- `0x18000bb28`
- `0x18000cd08`
- `0x18000dc70`
- `0x18000e2c0`
- `0x18000e610`
- `0x18000f270`
- `0x180010900`
- `0x180012430`
- `0x180012e00`
- `0x180012f94`
- `0x1800130c8`
- `0x180014528`
- `0x180014b20`
- `0x180014bb0`
- `0x180014c40`
- `0x180014d08`
- `0x180014df0`
- `0x180016320`
- `0x1800164b0`
- `0x1800174bc`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x18000cdc0  mov     [rsp+arg_0], rcx
0x18000cdc5  mov     rax, [rsp+arg_0]
0x18000cdca  mov     rax, [rax]
0x18000cdcd  retn
```
