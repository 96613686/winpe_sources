# ATL::CComContainedObject<CIdentityStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800119d0`
- end: `0x1800119e9`
- name: `?QueryInterface@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119f0`
- `0x180011a00`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityStore>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x1800119d0  sub     rsp, 28h
0x1800119d4  mov     rcx, [rcx+18h]
0x1800119d8  mov     rax, [rcx]
0x1800119db  mov     rax, [rax]
0x1800119de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119e3  nop
0x1800119e4  add     rsp, 28h
0x1800119e8  retn
```
