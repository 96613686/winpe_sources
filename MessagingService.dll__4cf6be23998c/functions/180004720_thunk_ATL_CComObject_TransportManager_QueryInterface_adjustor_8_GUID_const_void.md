# [thunk]:ATL::CComObject<TransportManager>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180004720`
- end: `0x180004729`
- name: `?QueryInterface@?$CComObject@VTransportManager@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004700`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<TransportManager>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180004720  sub     rcx, 8
0x180004724  jmp     ?QueryInterface@?$CComObject@VTransportManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<TransportManager>::QueryInterface(_GUID const &,void * *)
```
