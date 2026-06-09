# ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009340`
- end: `0x18000934f`
- name: `?QueryInterface@?$CComContainedObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceElevatedHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180009340  mov     rcx, [rcx+8]
0x180009344  mov     rax, [rcx]
0x180009347  mov     rax, [rax]
0x18000934a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
