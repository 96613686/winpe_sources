# [thunk]:ATL::CComContainedObject<CIdentityStore>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800119f0`
- end: `0x1800119f9`
- name: `?QueryInterface@?$CComContainedObject@VCIdentityStore@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800119d0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityStore>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CIdentityStore>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800119f0  sub     rcx, 8
0x1800119f4  jmp     ?QueryInterface@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CIdentityStore>::QueryInterface(_GUID const &,void * *)
```
