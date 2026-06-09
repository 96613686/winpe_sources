# ATL::CComContainedObject<CAddMdmObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005750`
- end: `0x18000575f`
- name: `?QueryInterface@?$CComContainedObject@VCAddMdmObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAddMdmObj>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005750  mov     rcx, [rcx+8]
0x180005754  mov     rax, [rcx]
0x180005757  mov     rax, [rax]
0x18000575a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
