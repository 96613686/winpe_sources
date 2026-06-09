# __generateMmsConfigurationNode_::_1_::dtor$2

- ea: `0x1800138d5`
- end: `0x1800138e1`
- name: `__generateMmsConfigurationNode_::_1_::dtor$2`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, VARIANTARG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003314`

## pseudocode

```c
HRESULT __fastcall _generateMmsConfigurationNode_::_1_::dtor_2(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 2);
}

```

## disassembly

```asm
0x1800138d5  lea     rcx, [rdx+30h]; pvarg
0x1800138dc  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
