# AutoDeleteFileStream::Write(void const *,ulong,ulong *)

- ea: `0x14000dd20`
- end: `0x14000dd39`
- name: `?Write@AutoDeleteFileStream@@UEAAJPEBXKPEAK@Z`
- size: `25`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *this, const void *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::Write(
        AutoDeleteFileStream *this,
        const void *a2,
        __int64 a3,
        unsigned int *a4)
{
  return (*(__int64 (__fastcall **)(_QWORD, const void *, __int64, unsigned int *))(**((_QWORD **)this + 6) + 32LL))(
           *((_QWORD *)this + 6),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x14000dd20  sub     rsp, 38h
0x14000dd24  mov     rcx, [rcx+30h]
0x14000dd28  mov     rax, [rcx]
0x14000dd2b  mov     rax, [rax+20h]
0x14000dd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd34  add     rsp, 38h
0x14000dd38  retn
```
