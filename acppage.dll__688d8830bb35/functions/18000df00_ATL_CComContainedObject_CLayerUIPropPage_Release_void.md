# ATL::CComContainedObject<CLayerUIPropPage>::Release(void)

- ea: `0x18000df00`
- end: `0x18000df10`
- name: `?Release@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df20`
- `0x18000df30`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CLayerUIPropPage>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x18000df00  mov     rcx, [rcx+18h]
0x18000df04  mov     rax, [rcx]
0x18000df07  mov     rax, [rax+10h]
0x18000df0b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
