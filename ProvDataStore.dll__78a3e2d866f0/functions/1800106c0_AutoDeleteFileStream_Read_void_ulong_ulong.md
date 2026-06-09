# AutoDeleteFileStream::Read(void *,ulong,ulong *)

- ea: `0x1800106c0`
- end: `0x1800106d9`
- name: `?Read@AutoDeleteFileStream@@UEAAJPEAXKPEAK@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, void *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Read(AutoDeleteFileStream *this, void *a2, __int64 a3, unsigned int *a4)
{
  return (*(__int64 (__fastcall **)(_QWORD, void *, __int64, unsigned int *))(**((_QWORD **)this + 6) + 24LL))(
           *((_QWORD *)this + 6),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x1800106c0  sub     rsp, 38h
0x1800106c4  mov     rcx, [rcx+30h]
0x1800106c8  mov     rax, [rcx]
0x1800106cb  mov     rax, [rax+18h]
0x1800106cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d4  add     rsp, 38h
0x1800106d8  retn
```
