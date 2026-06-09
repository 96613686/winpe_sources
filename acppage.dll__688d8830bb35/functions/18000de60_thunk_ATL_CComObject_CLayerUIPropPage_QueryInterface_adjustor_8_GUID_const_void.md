# [thunk]:ATL::CComObject<CLayerUIPropPage>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000de60`
- end: `0x18000de69`
- name: `?QueryInterface@?$CComObject@VCLayerUIPropPage@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000de40`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CLayerUIPropPage>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CLayerUIPropPage>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000de60  sub     rcx, 8
0x18000de64  jmp     ?QueryInterface@?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CLayerUIPropPage>::QueryInterface(_GUID const &,void * *)
```
