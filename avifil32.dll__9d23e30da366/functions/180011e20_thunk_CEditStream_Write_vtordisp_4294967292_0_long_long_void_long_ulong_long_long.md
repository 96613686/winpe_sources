# [thunk]:CEditStream::Write`vtordisp{4294967292,0}' (long,long,void *,long,ulong,long *,long *)

- ea: `0x180011e20`
- end: `0x180011e2c`
- name: `?Write@CEditStream@@$4PPPPPPPM@A@EAAJJJPEAXJKPEAJ1@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800062a0`

## pseudocode

```c
__int64 __fastcall CEditStream::Write(__int64 a1)
{
  return CAVICmpStream::CS::Delete((CAVICmpStream::CS *)(a1 - *(int *)(a1 - 4)));
}

```

## disassembly

```asm
0x180011e20  movsxd  rax, dword ptr [rcx-4]
0x180011e24  sub     rcx, rax; this
0x180011e27  jmp     ?Delete@CS@CAVICmpStream@@UEAAJJJ@Z; CAVICmpStream::CS::Delete(long,long)
```
