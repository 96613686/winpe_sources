# AutoDeleteFileStream::Read(void *,ulong,ulong *)

- ea: `0x14000d6d0`
- end: `0x14000d6e9`
- name: `?Read@AutoDeleteFileStream@@UEAAJPEAXKPEAK@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, void *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

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
0x14000d6d0  sub     rsp, 38h
0x14000d6d4  mov     rcx, [rcx+30h]
0x14000d6d8  mov     rax, [rcx]
0x14000d6db  mov     rax, [rax+18h]
0x14000d6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6e4  add     rsp, 38h
0x14000d6e8  retn
```
