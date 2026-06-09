# AutoDeleteFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180010970`
- end: `0x180010980`
- name: `?Stat@AutoDeleteFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `16`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, struct tagSTATSTG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Stat(AutoDeleteFileStream *this, struct tagSTATSTG *a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, struct tagSTATSTG *))(**((_QWORD **)this + 6) + 96LL))(
           *((_QWORD *)this + 6),
           a2);
}

```

## disassembly

```asm
0x180010970  mov     rcx, [rcx+30h]
0x180010974  mov     rax, [rcx]
0x180010977  mov     rax, [rax+60h]
0x18001097b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
