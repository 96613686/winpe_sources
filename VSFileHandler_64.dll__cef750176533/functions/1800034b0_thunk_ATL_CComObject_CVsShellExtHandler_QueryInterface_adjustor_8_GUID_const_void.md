# [thunk]:ATL::CComObject<CVsShellExtHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800034b0`
- end: `0x1800034b9`
- name: `?QueryInterface@?$CComObject@VCVsShellExtHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800031f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CVsShellExtHandler>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x1800034b0  sub     rcx, 8
0x1800034b4  jmp     ?QueryInterface@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)
```
