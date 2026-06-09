# ATL::CComContainedObject<COpusDecMFT>::QueryInterface(_GUID const &,void * *)

- ea: `0x180020e80`
- end: `0x180020e9c`
- name: `?QueryInterface@?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020eb0`

## callees

- `0x180024010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<COpusDecMFT>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 160))(*(_QWORD *)(a1 + 160));
}

```

## disassembly

```asm
0x180020e80  sub     rsp, 28h
0x180020e84  mov     rcx, [rcx+0A0h]
0x180020e8b  mov     rax, [rcx]
0x180020e8e  mov     rax, [rax]
0x180020e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e96  nop
0x180020e97  add     rsp, 28h
0x180020e9b  retn
```
