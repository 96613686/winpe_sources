# _CCommandHandler::Initialize_::_1_::dtor$0

- ea: `0x18000bd8c`
- end: `0x18000bd98`
- name: `_CCommandHandler::Initialize_::_1_::dtor$0`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, VARIANTARG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a6f8`

## pseudocode

```c
HRESULT __fastcall CCommandHandler::Initialize_::_1_::dtor_0(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 2);
}

```

## disassembly

```asm
0x18000bd8c  lea     rcx, [rdx+30h]; pvarg
0x18000bd93  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
