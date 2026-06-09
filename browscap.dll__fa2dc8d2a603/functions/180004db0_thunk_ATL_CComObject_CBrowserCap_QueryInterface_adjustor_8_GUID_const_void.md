# [thunk]:ATL::CComObject<CBrowserCap>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180004db0`
- end: `0x180004db9`
- name: `?QueryInterface@?$CComObject@VCBrowserCap@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004d90`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBrowserCap>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CBrowserCap>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180004db0  sub     rcx, 8
0x180004db4  jmp     ?QueryInterface@?$CComObject@VCBrowserCap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CBrowserCap>::QueryInterface(_GUID const &,void * *)
```
