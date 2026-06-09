# _CBrowserFactory::CreateInstance_::_1_::dtor$7

- ea: `0x18000be96`
- end: `0x18000bea2`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074dc`

## pseudocode

```c
HRESULT __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 272));
}

```

## disassembly

```asm
0x18000be96  lea     rcx, [rdx+110h]; pvarg
0x18000be9d  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
