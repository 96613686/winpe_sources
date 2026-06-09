# ATL::CComContainedObject<CRemMdmObj>::AddRef(void)

- ea: `0x180005280`
- end: `0x180005290`
- name: `?AddRef@?$CComContainedObject@VCRemMdmObj@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemMdmObj>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005280  mov     rcx, [rcx+8]
0x180005284  mov     rax, [rcx]
0x180005287  mov     rax, [rax+8]
0x18000528b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
