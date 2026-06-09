# CILogWrite::QueryInterface(_GUID const &,void * *)

- ea: `0x180002bd0`
- end: `0x180002bdf`
- name: `?QueryInterface@CILogWrite@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CILogWrite *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogWrite::QueryInterface(CILogWrite *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 1))(
           *((_QWORD *)this + 1),
           a2,
           a3);
}

```

## disassembly

```asm
0x180002bd0  mov     rcx, [rcx+8]
0x180002bd4  mov     rax, [rcx]
0x180002bd7  mov     rax, [rax]
0x180002bda  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
