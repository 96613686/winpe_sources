# [thunk]:ATL::CComObject<CLayerUIPropPage>::Release`adjustor{8}' (void)

- ea: `0x18000dfc0`
- end: `0x18000dfc9`
- name: `?Release@?$CComObject@VCLayerUIPropPage@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000df40`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CLayerUIPropPage>::Release(__int64 a1)
{
  return ATL::CComObject<CLayerUIPropPage>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000dfc0  sub     rcx, 8
0x18000dfc4  jmp     ?Release@?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComObject<CLayerUIPropPage>::Release(void)
```
