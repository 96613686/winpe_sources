# ATL::CComContainedObject<CLayerUIPropPage>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000de00`
- end: `0x18000de0f`
- name: `?QueryInterface@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000de20`
- `0x18000de30`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CLayerUIPropPage>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x18000de00  mov     rcx, [rcx+18h]
0x18000de04  mov     rax, [rcx]
0x18000de07  mov     rax, [rax]
0x18000de0a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
