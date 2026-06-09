# [thunk]:ATL::CComObject<CCompatContextMenu>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180009950`
- end: `0x180009959`
- name: `?QueryInterface@?$CComObject@VCCompatContextMenu@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009920`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCompatContextMenu>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CCompatContextMenu>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x180009950  sub     rcx, 10h
0x180009954  jmp     ?QueryInterface@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CCompatContextMenu>::QueryInterface(_GUID const &,void * *)
```
