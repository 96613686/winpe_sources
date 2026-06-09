# _CBrowserFactory::CreateInstance_::_1_::dtor$3

- ea: `0x18000be4e`
- end: `0x18000be5a`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074dc`

## pseudocode

```c
HRESULT __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 112));
}

```

## disassembly

```asm
0x18000be4e  lea     rcx, [rdx+70h]; pvarg
0x18000be55  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
