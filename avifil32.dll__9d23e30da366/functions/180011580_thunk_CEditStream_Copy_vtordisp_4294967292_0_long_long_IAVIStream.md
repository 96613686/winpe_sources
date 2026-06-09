# [thunk]:CEditStream::Copy`vtordisp{4294967292,0}' (long *,long *,IAVIStream * *)

- ea: `0x180011580`
- end: `0x18001158c`
- name: `?Copy@CEditStream@@$4PPPPPPPM@A@EAAJPEAJ0PEAPEAUIAVIStream@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180011594`

## pseudocode

```c
__int64 __fastcall CEditStream::Copy(__int64 a1, int *a2, int *a3, struct IAVIStream **a4)
{
  return CEditStream::Copy((CEditStream *)(a1 - *(int *)(a1 - 4)), a2, a3, a4);
}

```

## disassembly

```asm
0x180011580  movsxd  rax, dword ptr [rcx-4]
0x180011584  sub     rcx, rax; this
0x180011587  jmp     ?Copy@CEditStream@@UEAAJPEAJ0PEAPEAUIAVIStream@@@Z; CEditStream::Copy(long *,long *,IAVIStream * *)
```
