# [thunk]:ATL::CComContainedObject<CLayerUIPropPage>::Release`adjustor{8}' (void)

- ea: `0x18000df20`
- end: `0x18000df29`
- name: `?Release@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@W7EAAKXZ`
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
  return ATL::CComContainedObject<CLayerUIPropPage>::Release(a1 - 8);
}

```

## disassembly

```asm
0x18000df20  sub     rcx, 8
0x18000df24  jmp     ?Release@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CLayerUIPropPage>::Release(void)
```
