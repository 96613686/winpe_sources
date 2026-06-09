# _CBrowserFactory::CreateInstance_::_1_::dtor$6

- ea: `0x18000be84`
- end: `0x18000be90`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074dc`

## pseudocode

```c
HRESULT __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 176));
}

```

## disassembly

```asm
0x18000be84  lea     rcx, [rdx+0B0h]; pvarg
0x18000be8b  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
