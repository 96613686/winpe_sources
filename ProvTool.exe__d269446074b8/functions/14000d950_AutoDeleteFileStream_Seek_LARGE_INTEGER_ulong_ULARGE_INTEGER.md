# AutoDeleteFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x14000d950`
- end: `0x14000d969`
- name: `?Seek@AutoDeleteFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, union _LARGE_INTEGER, __int64, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

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
0x14000d950  sub     rsp, 38h
0x14000d954  mov     rcx, [rcx+30h]
0x14000d958  mov     rax, [rcx]
0x14000d95b  mov     rax, [rax+28h]
0x14000d95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d964  add     rsp, 38h
0x14000d968  retn
```
