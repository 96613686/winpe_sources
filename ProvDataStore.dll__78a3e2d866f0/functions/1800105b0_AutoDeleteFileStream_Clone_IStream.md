# AutoDeleteFileStream::Clone(IStream * *)

- ea: `0x1800105b0`
- end: `0x1800105c0`
- name: `?Clone@AutoDeleteFileStream@@UEAAJPEAPEAUIStream@@@Z`
- size: `16`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Clone(AutoDeleteFileStream *this, struct IStream **a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, struct IStream **))(**((_QWORD **)this + 6) + 104LL))(
           *((_QWORD *)this + 6),
           a2);
}

```

## disassembly

```asm
0x1800105b0  mov     rcx, [rcx+30h]
0x1800105b4  mov     rax, [rcx]
0x1800105b7  mov     rax, [rax+68h]
0x1800105bb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
