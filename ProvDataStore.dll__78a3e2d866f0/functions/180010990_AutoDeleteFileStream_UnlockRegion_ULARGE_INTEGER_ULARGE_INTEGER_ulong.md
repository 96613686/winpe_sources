# AutoDeleteFileStream::UnlockRegion(_ULARGE_INTEGER,_ULARGE_INTEGER,ulong)

- ea: `0x180010990`
- end: `0x1800109a9`
- name: `?UnlockRegion@AutoDeleteFileStream@@UEAAJT_ULARGE_INTEGER@@0K@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, union _ULARGE_INTEGER, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::UnlockRegion(
        AutoDeleteFileStream *this,
        union _ULARGE_INTEGER a2,
        union _ULARGE_INTEGER a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, union _ULARGE_INTEGER, union _ULARGE_INTEGER))(**((_QWORD **)this + 6) + 88LL))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x180010990  sub     rsp, 38h
0x180010994  mov     rcx, [rcx+30h]
0x180010998  mov     rax, [rcx]
0x18001099b  mov     rax, [rax+58h]
0x18001099f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a4  add     rsp, 38h
0x1800109a8  retn
```
