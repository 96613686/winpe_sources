# [thunk]:ATL::CComContainedObject<CLayerUIPropPage>::AddRef`adjustor{16}' (void)

- ea: `0x18000aa40`
- end: `0x18000aa49`
- name: `?AddRef@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CLayerUIPropPage>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x18000aa40  sub     rcx, 10h
0x18000aa44  jmp     ?AddRef@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CLayerUIPropPage>::AddRef(void)
```
