# [thunk]:ATL::CComContainedObject<CRASrv>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x140008840`
- end: `0x140008849`
- name: `?QueryInterface@?$CComContainedObject@VCRASrv@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008820`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRASrv>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CRASrv>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x140008840  sub     rcx, 8
0x140008844  jmp     ?QueryInterface@?$CComContainedObject@VCRASrv@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CRASrv>::QueryInterface(_GUID const &,void * *)
```
