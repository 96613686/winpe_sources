# __parseRouteSelectionDescriptors_::_1_::dtor$0

- ea: `0x18001391d`
- end: `0x180013929`
- name: `__parseRouteSelectionDescriptors_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030d8`

## pseudocode

```c
__int64 __fastcall _parseRouteSelectionDescriptors_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x18001391d  lea     rcx, [rdx+28h]
0x180013924  jmp     ??1?$CComPtr@UIXMLDOMNodeList@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMNodeList>::~CComPtr<IXMLDOMNodeList>(void)
```
