# ATL::CComContainedObject<MetadataPackageSource>::Release(void)

- ea: `0x180011ca0`
- end: `0x180011cb0`
- name: `?Release@?$CComContainedObject@VMetadataPackageSource@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<MetadataPackageSource>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 16LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180011ca0  mov     rcx, [rcx+8]
0x180011ca4  mov     rax, [rcx]
0x180011ca7  mov     rax, [rax+10h]
0x180011cab  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
