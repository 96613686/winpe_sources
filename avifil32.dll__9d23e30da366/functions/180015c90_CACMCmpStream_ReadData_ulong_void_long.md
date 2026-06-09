# CACMCmpStream::ReadData(ulong,void *,long *)

- ea: `0x180015c90`
- end: `0x180015cac`
- name: `?ReadData@CACMCmpStream@@UEAAJKPEAXPEAJ@Z`
- size: `28`
- prototype: `__int64 __fastcall(CACMCmpStream *__hidden this, unsigned int, void *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall CACMCmpStream::ReadData(CACMCmpStream *this, __int64 a2, void *a3, int *a4)
{
  return (*(__int64 (__fastcall **)(_QWORD, __int64, void *, int *))(**((_QWORD **)this + 28) + 88LL))(
           *((_QWORD *)this + 28),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x180015c90  sub     rsp, 38h
0x180015c94  mov     rcx, [rcx+0E0h]
0x180015c9b  mov     rax, [rcx]
0x180015c9e  mov     rax, [rax+58h]
0x180015ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca7  add     rsp, 38h
0x180015cab  retn
```
