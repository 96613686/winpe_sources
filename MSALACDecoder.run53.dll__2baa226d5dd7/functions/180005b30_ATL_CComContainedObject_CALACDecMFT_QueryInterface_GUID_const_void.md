# ATL::CComContainedObject<CALACDecMFT>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005b30`
- end: `0x180005b4c`
- name: `?QueryInterface@?$CComContainedObject@VCALACDecMFT@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CALACDecMFT>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 152))(*(_QWORD *)(a1 + 152));
}

```

## disassembly

```asm
0x180005b30  sub     rsp, 28h
0x180005b34  mov     rcx, [rcx+98h]
0x180005b3b  mov     rax, [rcx]
0x180005b3e  mov     rax, [rax]
0x180005b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b46  nop
0x180005b47  add     rsp, 28h
0x180005b4b  retn
```
