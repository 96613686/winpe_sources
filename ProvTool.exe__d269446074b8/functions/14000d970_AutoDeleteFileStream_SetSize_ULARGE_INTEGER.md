# AutoDeleteFileStream::SetSize(_ULARGE_INTEGER)

- ea: `0x14000d970`
- end: `0x14000d980`
- name: `?SetSize@AutoDeleteFileStream@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `16`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::SetSize(AutoDeleteFileStream *this, union _ULARGE_INTEGER a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, union _ULARGE_INTEGER))(**((_QWORD **)this + 6) + 48LL))(
           *((_QWORD *)this + 6),
           a2);
}

```

## disassembly

```asm
0x14000d970  mov     rcx, [rcx+30h]
0x14000d974  mov     rax, [rcx]
0x14000d977  mov     rax, [rax+30h]
0x14000d97b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
