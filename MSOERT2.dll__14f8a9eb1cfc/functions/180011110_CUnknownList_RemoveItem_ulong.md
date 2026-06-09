# CUnknownList::RemoveItem(ulong)

- ea: `0x180011110`
- end: `0x180011120`
- name: `?RemoveItem@CUnknownList@@UEAAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(CUnknownList *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall CUnknownList::RemoveItem(CUnknownList *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180011110  mov     rcx, [rcx+8]
0x180011114  mov     rax, [rcx]
0x180011117  mov     rax, [rax+38h]
0x18001111b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
