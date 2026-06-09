# AutoDeleteFileStream::LockRegion(_ULARGE_INTEGER,_ULARGE_INTEGER,ulong)

- ea: `0x14000d630`
- end: `0x14000d649`
- name: `?LockRegion@AutoDeleteFileStream@@UEAAJT_ULARGE_INTEGER@@0K@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, union _ULARGE_INTEGER, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::LockRegion(
        AutoDeleteFileStream *this,
        union _ULARGE_INTEGER a2,
        union _ULARGE_INTEGER a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, union _ULARGE_INTEGER, union _ULARGE_INTEGER))(**((_QWORD **)this + 6) + 80LL))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x14000d630  sub     rsp, 38h
0x14000d634  mov     rcx, [rcx+30h]
0x14000d638  mov     rax, [rcx]
0x14000d63b  mov     rax, [rax+50h]
0x14000d63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d644  add     rsp, 38h
0x14000d648  retn
```
