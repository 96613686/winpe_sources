# _CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor$0

- ea: `0x14001bec3`
- end: `0x14001becf`
- name: `_CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b118`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GenerateXMLModelFilesNode_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>((__int64 *)(a2 + 176));
}

```

## disassembly

```asm
0x14001bec3  lea     rcx, [rdx+0B0h]
0x14001beca  jmp     ??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)
```
