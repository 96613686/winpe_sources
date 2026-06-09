# ATL::CComContainedObject<CIdentityProfileHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800119b0`
- end: `0x1800119c9`
- name: `?QueryInterface@?$CComContainedObject@VCIdentityProfileHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityProfileHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1800119b0  sub     rsp, 28h
0x1800119b4  mov     rcx, [rcx+8]
0x1800119b8  mov     rax, [rcx]
0x1800119bb  mov     rax, [rax]
0x1800119be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c3  nop
0x1800119c4  add     rsp, 28h
0x1800119c8  retn
```
