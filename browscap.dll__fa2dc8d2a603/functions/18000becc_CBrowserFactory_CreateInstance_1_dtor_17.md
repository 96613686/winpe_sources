# _CBrowserFactory::CreateInstance_::_1_::dtor$17

- ea: `0x18000becc`
- end: `0x18000bed8`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$17`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021d0`

## pseudocode

```c
void __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 80));
}

```

## disassembly

```asm
0x18000becc  lea     rcx, [rdx+50h]; this
0x18000bed3  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
