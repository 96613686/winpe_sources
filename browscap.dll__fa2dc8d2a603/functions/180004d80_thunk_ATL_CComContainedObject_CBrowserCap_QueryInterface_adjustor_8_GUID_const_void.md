# [thunk]:ATL::CComContainedObject<CBrowserCap>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180004d80`
- end: `0x180004d89`
- name: `?QueryInterface@?$CComContainedObject@VCBrowserCap@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004d60`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CBrowserCap>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180004d80  sub     rcx, 8
0x180004d84  jmp     ?QueryInterface@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CBrowserCap>::QueryInterface(_GUID const &,void * *)
```
