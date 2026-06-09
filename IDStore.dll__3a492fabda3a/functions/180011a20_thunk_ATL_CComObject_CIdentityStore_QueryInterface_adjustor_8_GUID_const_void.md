# [thunk]:ATL::CComObject<CIdentityStore>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180011a20`
- end: `0x180011a29`
- name: `?QueryInterface@?$CComObject@VCIdentityStore@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aa30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityStore>::QueryInterface(__int64 a1, _DWORD *a2, char **a3)
{
  return ATL::CComObject<CIdentityStore>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180011a20  sub     rcx, 8
0x180011a24  jmp     ?QueryInterface@?$CComObject@VCIdentityStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CIdentityStore>::QueryInterface(_GUID const &,void * *)
```
