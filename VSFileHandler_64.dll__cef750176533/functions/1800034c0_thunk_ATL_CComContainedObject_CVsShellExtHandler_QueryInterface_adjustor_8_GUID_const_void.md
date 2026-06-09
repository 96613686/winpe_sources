# [thunk]:ATL::CComContainedObject<CVsShellExtHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800034c0`
- end: `0x1800034c9`
- name: `?QueryInterface@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003280`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CVsShellExtHandler>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800034c0  sub     rcx, 8
0x1800034c4  jmp     ?QueryInterface@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)
```
