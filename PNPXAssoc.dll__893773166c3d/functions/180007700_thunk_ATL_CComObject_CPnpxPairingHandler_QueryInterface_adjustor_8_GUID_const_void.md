# [thunk]:ATL::CComObject<CPnpxPairingHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007700`
- end: `0x180007709`
- name: `?QueryInterface@?$CComObject@VCPnpxPairingHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpxPairingHandler>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CPnpxPairingHandler>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180007700  sub     rcx, 8
0x180007704  jmp     ?QueryInterface@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CPnpxPairingHandler>::QueryInterface(_GUID const &,void * *)
```
