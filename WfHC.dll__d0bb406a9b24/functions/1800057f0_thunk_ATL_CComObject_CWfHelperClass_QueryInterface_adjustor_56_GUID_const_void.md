# [thunk]:ATL::CComObject<CWfHelperClass>::QueryInterface`adjustor{56}' (_GUID const &,void * *)

- ea: `0x1800057f0`
- end: `0x1800057f9`
- name: `?QueryInterface@?$CComObject@VCWfHelperClass@@@ATL@@WDI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800057c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWfHelperClass>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CWfHelperClass>::QueryInterface((char *)(a1 - 56), a2, a3);
}

```

## disassembly

```asm
0x1800057f0  sub     rcx, 38h ; '8'
0x1800057f4  jmp     ?QueryInterface@?$CComObject@VCWfHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CWfHelperClass>::QueryInterface(_GUID const &,void * *)
```
