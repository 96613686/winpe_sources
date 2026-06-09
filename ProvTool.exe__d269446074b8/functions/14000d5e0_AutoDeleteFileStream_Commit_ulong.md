# AutoDeleteFileStream::Commit(ulong)

- ea: `0x14000d5e0`
- end: `0x14000d5f0`
- name: `?Commit@AutoDeleteFileStream@@UEAAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Commit(AutoDeleteFileStream *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x14000d5e0  mov     rcx, [rcx+30h]
0x14000d5e4  mov     rax, [rcx]
0x14000d5e7  mov     rax, [rax+40h]
0x14000d5eb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
