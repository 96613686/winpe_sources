# _CGenerateComment::AddFooter_::_1_::dtor$0

- ea: `0x140015e55`
- end: `0x140015e61`
- name: `_CGenerateComment::AddFooter_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007964`

## pseudocode

```c
void __fastcall CGenerateComment::AddFooter_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 56));
}

```

## disassembly

```asm
0x140015e55  lea     rcx, [rdx+38h]; this
0x140015e5c  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
