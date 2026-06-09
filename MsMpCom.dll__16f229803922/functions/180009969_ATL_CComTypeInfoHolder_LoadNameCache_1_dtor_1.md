# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$1

- ea: `0x180009969`
- end: `0x180009975`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021c0`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 160));
}

```

## disassembly

```asm
0x180009969  lea     rcx, [rdx+0A0h]; this
0x180009970  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
