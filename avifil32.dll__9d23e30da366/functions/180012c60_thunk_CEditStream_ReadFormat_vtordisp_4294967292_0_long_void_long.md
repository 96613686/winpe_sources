# [thunk]:CEditStream::ReadFormat`vtordisp{4294967292,0}' (long,void *,long *)

- ea: `0x180012c60`
- end: `0x180012c6c`
- name: `?ReadFormat@CEditStream@@$4PPPPPPPM@A@EAAJJPEAXPEAJ@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012c74`

## pseudocode

```c
__int64 __fastcall CEditStream::ReadFormat(__int64 a1, int a2, void *a3, int *a4)
{
  return CEditStream::ReadFormat((CEditStream *)(a1 - *(int *)(a1 - 4)), a2, a3, a4);
}

```

## disassembly

```asm
0x180012c60  movsxd  rax, dword ptr [rcx-4]
0x180012c64  sub     rcx, rax; this
0x180012c67  jmp     ?ReadFormat@CEditStream@@UEAAJJPEAXPEAJ@Z; CEditStream::ReadFormat(long,void *,long *)
```
