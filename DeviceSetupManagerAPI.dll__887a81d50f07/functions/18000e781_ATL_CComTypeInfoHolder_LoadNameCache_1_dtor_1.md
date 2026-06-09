# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$1

- ea: `0x18000e781`
- end: `0x18000e78d`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003560`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 160));
}

```

## disassembly

```asm
0x18000e781  lea     rcx, [rdx+0A0h]; this
0x18000e788  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
