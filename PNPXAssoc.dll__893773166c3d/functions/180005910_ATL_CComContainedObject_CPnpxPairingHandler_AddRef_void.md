# ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(void)

- ea: `0x180005910`
- end: `0x180005920`
- name: `?AddRef@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005930`
- `0x180005940`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180005910  mov     rcx, [rcx+18h]
0x180005914  mov     rax, [rcx]
0x180005917  mov     rax, [rax+8]
0x18000591b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
