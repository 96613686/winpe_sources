# ATL::CComContainedObject<CRemoveDeviceContextHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009310`
- end: `0x18000931f`
- name: `?QueryInterface@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009330`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceContextHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180009310  mov     rcx, [rcx+10h]
0x180009314  mov     rax, [rcx]
0x180009317  mov     rax, [rax]
0x18000931a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
