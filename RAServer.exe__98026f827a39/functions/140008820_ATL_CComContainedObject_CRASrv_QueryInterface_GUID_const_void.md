# ATL::CComContainedObject<CRASrv>::QueryInterface(_GUID const &,void * *)

- ea: `0x140008820`
- end: `0x140008839`
- name: `?QueryInterface@?$CComContainedObject@VCRASrv@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008840`

## callees

- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRASrv>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x140008820  sub     rsp, 28h
0x140008824  mov     rcx, [rcx+10h]
0x140008828  mov     rax, [rcx]
0x14000882b  mov     rax, [rax]
0x14000882e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008833  nop
0x140008834  add     rsp, 28h
0x140008838  retn
```
