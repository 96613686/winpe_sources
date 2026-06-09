# [thunk]:ATL::CComObject<CConnectedUserStore>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180011a10`
- end: `0x180011a19`
- name: `?QueryInterface@?$CComObject@VCConnectedUserStore@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bc50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::QueryInterface(__int64 a1, _DWORD *a2, char **a3)
{
  return ATL::CComObject<CConnectedUserStore>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180011a10  sub     rcx, 8
0x180011a14  jmp     ?QueryInterface@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CConnectedUserStore>::QueryInterface(_GUID const &,void * *)
```
