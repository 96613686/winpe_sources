# __SetBindingDeviceInterfacePath_::_1_::dtor$0

- ea: `0x180011ab7`
- end: `0x180011ac3`
- name: `__SetBindingDeviceInterfacePath_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009170`

## pseudocode

```c
void __fastcall _SetBindingDeviceInterfacePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 64));
}

```

## disassembly

```asm
0x180011ab7  lea     rcx, [rdx+40h]; this
0x180011abe  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
