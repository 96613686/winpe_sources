# ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(void)

- ea: `0x140011a54`
- end: `0x140011a66`
- name: `??1?$CComPtr@UIXMLDOMNamedNodeMap@@@ATL@@QEAA@XZ`
- size: `18`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014f25`
- `0x140014f75`
- `0x140014f9d`
- `0x140014fdb`
- `0x140014ff1`
- `0x140015003`
- `0x140015053`
- `0x14001507f`
- `0x140015091`
- `0x1400150b9`
- `0x1400150cb`
- `0x140015101`
- `0x140015149`
- `0x14001516d`
- `0x140015227`
- `0x1400152b5`
- `0x14001533b`
- `0x140015363`

## callees

- `0x140011a6c`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IXMLDOMNamedNodeMap>::~CComPtr<IXMLDOMNamedNodeMap>(__int64 a1)
{
  return ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(a1);
}

```

## disassembly

```asm
0x140011a54  mov     [rsp+arg_0], rcx
0x140011a59  sub     rsp, 28h
0x140011a5d  add     rsp, 28h
0x140011a61  jmp     ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
```
