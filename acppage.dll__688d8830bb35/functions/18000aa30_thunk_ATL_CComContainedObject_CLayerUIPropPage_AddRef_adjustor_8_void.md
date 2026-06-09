# [thunk]:ATL::CComContainedObject<CLayerUIPropPage>::AddRef`adjustor{8}' (void)

- ea: `0x18000aa30`
- end: `0x18000aa39`
- name: `?AddRef@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aa10`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CLayerUIPropPage>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CLayerUIPropPage>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000aa30  sub     rcx, 8
0x18000aa34  jmp     ?AddRef@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CLayerUIPropPage>::AddRef(void)
```
