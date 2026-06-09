# AutoDeleteFileStream::Commit(ulong)

- ea: `0x1800105d0`
- end: `0x1800105e0`
- name: `?Commit@AutoDeleteFileStream@@UEAAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Commit(AutoDeleteFileStream *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x1800105d0  mov     rcx, [rcx+30h]
0x1800105d4  mov     rax, [rcx]
0x1800105d7  mov     rax, [rax+40h]
0x1800105db  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
