# [thunk]:ATL::CComContainedObject<CLayerUIPropPage>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000de20`
- end: `0x18000de29`
- name: `?QueryInterface@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000de00`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CLayerUIPropPage>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CLayerUIPropPage>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x18000de20  sub     rcx, 8
0x18000de24  jmp     ?QueryInterface@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CLayerUIPropPage>::QueryInterface(_GUID const &,void * *)
```
