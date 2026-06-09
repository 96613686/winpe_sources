# [thunk]:ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007670`
- end: `0x180007679`
- name: `?QueryInterface@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180007670  sub     rcx, 8
0x180007674  jmp     ?QueryInterface@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CPnpxPairingHandler>::QueryInterface(_GUID const &,void * *)
```
