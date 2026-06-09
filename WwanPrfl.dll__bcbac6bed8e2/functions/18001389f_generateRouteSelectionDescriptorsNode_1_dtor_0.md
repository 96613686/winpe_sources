# __generateRouteSelectionDescriptorsNode_::_1_::dtor$0

- ea: `0x18001389f`
- end: `0x1800138ab`
- name: `__generateRouteSelectionDescriptorsNode_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030d8`

## pseudocode

```c
__int64 __fastcall _generateRouteSelectionDescriptorsNode_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x18001389f  lea     rcx, [rdx+30h]
0x1800138a6  jmp     ??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)
```
