# _CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor$2

- ea: `0x14001bee7`
- end: `0x14001bef3`
- name: `_CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor$2`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, VARIANTARG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b264`

## pseudocode

```c
HRESULT __fastcall CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor_2(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 2);
}

```

## disassembly

```asm
0x14001bee7  lea     rcx, [rdx+30h]; pvarg
0x14001beee  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
