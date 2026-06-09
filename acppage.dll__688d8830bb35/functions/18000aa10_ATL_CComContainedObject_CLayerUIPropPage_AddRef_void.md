# ATL::CComContainedObject<CLayerUIPropPage>::AddRef(void)

- ea: `0x18000aa10`
- end: `0x18000aa20`
- name: `?AddRef@?$CComContainedObject@VCLayerUIPropPage@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aa30`
- `0x18000aa40`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CLayerUIPropPage>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x18000aa10  mov     rcx, [rcx+18h]
0x18000aa14  mov     rax, [rcx]
0x18000aa17  mov     rax, [rax+8]
0x18000aa1b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
