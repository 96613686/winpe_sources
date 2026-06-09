# ATL::CComContainedObject<CDfsShell>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800051d0`
- end: `0x1800051e9`
- name: `?QueryInterface@?$CComContainedObject@VCDfsShell@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800051f0`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDfsShell>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800051d0  sub     rsp, 28h
0x1800051d4  mov     rcx, [rcx+10h]
0x1800051d8  mov     rax, [rcx]
0x1800051db  mov     rax, [rax]
0x1800051de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e3  nop
0x1800051e4  add     rsp, 28h
0x1800051e8  retn
```
