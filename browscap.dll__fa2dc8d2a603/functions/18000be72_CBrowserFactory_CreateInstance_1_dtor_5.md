# _CBrowserFactory::CreateInstance_::_1_::dtor$5

- ea: `0x18000be72`
- end: `0x18000be7e`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074dc`

## pseudocode

```c
HRESULT __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 208));
}

```

## disassembly

```asm
0x18000be72  lea     rcx, [rdx+0D0h]; pvarg
0x18000be79  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
