# ATL::CComContainedObject<CMidi2BS2UMPTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800065d0`
- end: `0x1800065e9`
- name: `?QueryInterface@?$CComContainedObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMidi2BS2UMPTransform>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800065d0  sub     rsp, 28h
0x1800065d4  mov     rcx, [rcx+8]
0x1800065d8  mov     rax, [rcx]
0x1800065db  mov     rax, [rax]
0x1800065de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e3  nop
0x1800065e4  add     rsp, 28h
0x1800065e8  retn
```
