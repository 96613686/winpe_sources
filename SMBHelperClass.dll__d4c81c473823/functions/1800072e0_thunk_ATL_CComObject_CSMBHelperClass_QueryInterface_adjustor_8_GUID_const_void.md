# [thunk]:ATL::CComObject<CSMBHelperClass>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800072e0`
- end: `0x1800072e9`
- name: `?QueryInterface@?$CComObject@VCSMBHelperClass@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800072c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSMBHelperClass>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CSMBHelperClass>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x1800072e0  sub     rcx, 8
0x1800072e4  jmp     ?QueryInterface@?$CComObject@VCSMBHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CSMBHelperClass>::QueryInterface(_GUID const &,void * *)
```
