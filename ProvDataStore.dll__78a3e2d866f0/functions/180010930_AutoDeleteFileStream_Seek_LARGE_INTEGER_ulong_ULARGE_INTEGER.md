# AutoDeleteFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180010930`
- end: `0x180010949`
- name: `?Seek@AutoDeleteFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, union _LARGE_INTEGER, __int64, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Seek(
        AutoDeleteFileStream *this,
        union _LARGE_INTEGER a2,
        __int64 a3,
        union _ULARGE_INTEGER *a4)
{
  return (*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER, __int64, union _ULARGE_INTEGER *))(**((_QWORD **)this + 6) + 40LL))(
           *((_QWORD *)this + 6),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x180010930  sub     rsp, 38h
0x180010934  mov     rcx, [rcx+30h]
0x180010938  mov     rax, [rcx]
0x18001093b  mov     rax, [rax+28h]
0x18001093f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010944  add     rsp, 38h
0x180010948  retn
```
