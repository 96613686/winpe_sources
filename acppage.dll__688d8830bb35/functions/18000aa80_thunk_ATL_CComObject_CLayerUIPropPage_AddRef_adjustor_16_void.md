# [thunk]:ATL::CComObject<CLayerUIPropPage>::AddRef`adjustor{16}' (void)

- ea: `0x18000aa80`
- end: `0x18000aa89`
- name: `?AddRef@?$CComObject@VCLayerUIPropPage@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CLayerUIPropPage>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x18000aa80  sub     rcx, 10h
0x18000aa84  jmp     ?AddRef@?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComObject<CLayerUIPropPage>::AddRef(void)
```
