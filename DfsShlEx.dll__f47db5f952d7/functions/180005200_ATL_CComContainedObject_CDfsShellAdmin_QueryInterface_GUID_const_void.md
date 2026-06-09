# ATL::CComContainedObject<CDfsShellAdmin>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005200`
- end: `0x180005219`
- name: `?QueryInterface@?$CComContainedObject@VCDfsShellAdmin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShellAdmin>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x180005200  sub     rsp, 28h
0x180005204  mov     rcx, [rcx+8]
0x180005208  mov     rax, [rcx]
0x18000520b  mov     rax, [rax]
0x18000520e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005213  nop
0x180005214  add     rsp, 28h
0x180005218  retn
```
