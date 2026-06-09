# [thunk]:ATL::CComObject<CLayerUIPropPage>::AddRef`adjustor{8}' (void)

- ea: `0x18000aa70`
- end: `0x18000aa79`
- name: `?AddRef@?$CComObject@VCLayerUIPropPage@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CLayerUIPropPage>::AddRef(__int64 a1)
{
  return ATL::CComObject<CLayerUIPropPage>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000aa70  sub     rcx, 8
0x18000aa74  jmp     ?AddRef@?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComObject<CLayerUIPropPage>::AddRef(void)
```
