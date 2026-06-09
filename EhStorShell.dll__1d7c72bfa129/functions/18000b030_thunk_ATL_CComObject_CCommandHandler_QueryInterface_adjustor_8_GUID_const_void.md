# [thunk]:ATL::CComObject<CCommandHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000b030`
- end: `0x18000b039`
- name: `?QueryInterface@?$CComObject@VCCommandHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CCommandHandler>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000b030  sub     rcx, 8
0x18000b034  jmp     ?QueryInterface@?$CComObject@VCCommandHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCommandHandler>::QueryInterface(_GUID const &,void * *)
```
