# _CModelDownloadComponent::InitializeCopyJob_::_1_::dtor$0

- ea: `0x14001bf41`
- end: `0x14001bf4d`
- name: `_CModelDownloadComponent::InitializeCopyJob_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b118`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::InitializeCopyJob_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x14001bf41  lea     rcx, [rdx+80h]
0x14001bf48  jmp     ??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)
```
