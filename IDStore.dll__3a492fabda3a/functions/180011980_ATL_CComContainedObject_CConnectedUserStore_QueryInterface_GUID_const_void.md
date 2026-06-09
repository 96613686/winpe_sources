# ATL::CComContainedObject<CConnectedUserStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011980`
- end: `0x180011999`
- name: `?QueryInterface@?$CComContainedObject@VCConnectedUserStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119a0`

## callees

- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CConnectedUserStore>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180011980  sub     rsp, 28h
0x180011984  mov     rcx, [rcx+10h]
0x180011988  mov     rax, [rcx]
0x18001198b  mov     rax, [rax]
0x18001198e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011993  nop
0x180011994  add     rsp, 28h
0x180011998  retn
```
