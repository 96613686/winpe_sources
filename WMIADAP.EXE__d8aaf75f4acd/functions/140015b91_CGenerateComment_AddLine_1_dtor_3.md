# _CGenerateComment::AddLine_::_1_::dtor$3

- ea: `0x140015b91`
- end: `0x140015b9d`
- name: `_CGenerateComment::AddLine_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007964`

## pseudocode

```c
void __fastcall CGenerateComment::AddLine_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 104));
}

```

## disassembly

```asm
0x140015b91  lea     rcx, [rdx+68h]; this
0x140015b98  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
