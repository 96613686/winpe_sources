# [thunk]:ATL::CComObject<CEnhancedStorageFolder>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x180008d60`
- end: `0x180008d69`
- name: `?QueryInterface@?$CComObject@VCEnhancedStorageFolder@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001470`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageFolder>::QueryInterface(__int64 a1, _DWORD *a2, char **a3)
{
  return ATL::CComObject<CEnhancedStorageFolder>::QueryInterface(a1 - 24, a2, a3);
}

```

## disassembly

```asm
0x180008d60  sub     rcx, 18h
0x180008d64  jmp     ?QueryInterface@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CEnhancedStorageFolder>::QueryInterface(_GUID const &,void * *)
```
