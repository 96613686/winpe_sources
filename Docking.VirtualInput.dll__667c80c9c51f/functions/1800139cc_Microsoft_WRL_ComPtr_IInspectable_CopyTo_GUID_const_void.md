# Microsoft::WRL::ComPtr<IInspectable>::CopyTo(_GUID const &,void * *)

- ea: `0x1800139cc`
- end: `0x180013a28`
- name: `?CopyTo@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012e00`
- `0x180013a30`
- `0x180013bd0`

## callees

- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IInspectable>::CopyTo(_QWORD *a1, __int64 a2, __int64 a3)
{
  return (**(__int64 (__fastcall ***)(_QWORD, __int64, __int64))*a1)(*a1, a2, a3);
}

```

## disassembly

```asm
0x1800139cc  mov     [rsp+arg_10], r8
0x1800139d1  mov     [rsp+arg_8], rdx
0x1800139d6  mov     [rsp+arg_0], rcx
0x1800139db  sub     rsp, 48h
0x1800139df  mov     rax, [rsp+48h+arg_0]
0x1800139e4  mov     rax, [rax]
0x1800139e7  mov     [rsp+48h+var_20], rax
0x1800139ec  mov     rax, [rsp+48h+arg_0]
0x1800139f1  mov     rax, [rax]
0x1800139f4  mov     rax, [rax]
0x1800139f7  mov     rax, [rax]
0x1800139fa  mov     [rsp+48h+var_28], rax
0x1800139ff  mov     rax, [rsp+48h+var_28]
0x180013a04  mov     [rsp+48h+var_18], rax
0x180013a09  mov     r8, [rsp+48h+arg_10]
0x180013a0e  mov     rdx, [rsp+48h+arg_8]
0x180013a13  mov     rcx, [rsp+48h+var_20]
0x180013a18  mov     rax, [rsp+48h+var_18]
0x180013a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a22  nop
0x180013a23  add     rsp, 48h
0x180013a27  retn
```
