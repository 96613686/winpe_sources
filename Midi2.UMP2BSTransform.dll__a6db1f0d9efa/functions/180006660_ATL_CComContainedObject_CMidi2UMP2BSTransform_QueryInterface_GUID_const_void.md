# ATL::CComContainedObject<CMidi2UMP2BSTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006660`
- end: `0x180006679`
- name: `?QueryInterface@?$CComContainedObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2UMP2BSTransform>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180006660  sub     rsp, 28h
0x180006664  mov     rcx, [rcx+8]
0x180006668  mov     rax, [rcx]
0x18000666b  mov     rax, [rax]
0x18000666e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006673  nop
0x180006674  add     rsp, 28h
0x180006678  retn
```
