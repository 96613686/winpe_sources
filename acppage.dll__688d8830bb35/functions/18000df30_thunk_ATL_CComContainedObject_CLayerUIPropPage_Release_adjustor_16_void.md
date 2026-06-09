# [thunk]:ATL::CComContainedObject<CLayerUIPropPage>::Release`adjustor{16}' (void)

- ea: `0x18000df30`
- end: `0x18000df39`
- name: `?Release@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000df00`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CLayerUIPropPage>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CLayerUIPropPage>::Release(a1 - 16);
}

```

## disassembly

```asm
0x18000df30  sub     rcx, 10h
0x18000df34  jmp     ?Release@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CLayerUIPropPage>::Release(void)
```
