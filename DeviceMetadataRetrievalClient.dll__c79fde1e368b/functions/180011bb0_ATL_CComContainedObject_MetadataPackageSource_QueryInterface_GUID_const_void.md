# ATL::CComContainedObject<MetadataPackageSource>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011bb0`
- end: `0x180011bbf`
- name: `?QueryInterface@?$CComContainedObject@VMetadataPackageSource@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<MetadataPackageSource>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180011bb0  mov     rcx, [rcx+8]
0x180011bb4  mov     rax, [rcx]
0x180011bb7  mov     rax, [rax]
0x180011bba  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
