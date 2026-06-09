# [thunk]:ATL::CComContainedObject<CConnectedUserStore>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800119a0`
- end: `0x1800119a9`
- name: `?QueryInterface@?$CComContainedObject@VCConnectedUserStore@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011980`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CConnectedUserStore>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CConnectedUserStore>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800119a0  sub     rcx, 8
0x1800119a4  jmp     ?QueryInterface@?$CComContainedObject@VCConnectedUserStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CConnectedUserStore>::QueryInterface(_GUID const &,void * *)
```
