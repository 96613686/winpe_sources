# _CBrowserFactory::CreateInstance_::_1_::dtor$8

- ea: `0x18000bea8`
- end: `0x18000beb4`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074dc`

## pseudocode

```c
HRESULT __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 152));
}

```

## disassembly

```asm
0x18000bea8  lea     rcx, [rdx+98h]; pvarg
0x18000beaf  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
