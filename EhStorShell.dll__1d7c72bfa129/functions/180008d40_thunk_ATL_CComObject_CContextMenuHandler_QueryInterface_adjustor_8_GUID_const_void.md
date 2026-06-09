# [thunk]:ATL::CComObject<CContextMenuHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180008d40`
- end: `0x180008d49`
- name: `?QueryInterface@?$CComObject@VCContextMenuHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006540`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CContextMenuHandler>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180008d40  sub     rcx, 8
0x180008d44  jmp     ?QueryInterface@?$CComObject@VCContextMenuHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CContextMenuHandler>::QueryInterface(_GUID const &,void * *)
```
