# __generateRouteSelectionDescriptorsNode_::_1_::dtor$1

- ea: `0x1800138b1`
- end: `0x1800138bd`
- name: `__generateRouteSelectionDescriptorsNode_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030d8`

## pseudocode

```c
__int64 __fastcall _generateRouteSelectionDescriptorsNode_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x1800138b1  lea     rcx, [rdx+38h]
0x1800138b8  jmp     ??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)
```
