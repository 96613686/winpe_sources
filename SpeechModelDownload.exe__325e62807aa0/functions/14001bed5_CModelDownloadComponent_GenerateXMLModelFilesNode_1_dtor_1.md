# _CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor$1

- ea: `0x14001bed5`
- end: `0x14001bee1`
- name: `_CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b118`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>((__int64 *)(a2 + 168));
}

```

## disassembly

```asm
0x14001bed5  lea     rcx, [rdx+0A8h]
0x14001bedc  jmp     ??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)
```
