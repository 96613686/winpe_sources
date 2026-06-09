# [thunk]:CEditStream::Read`vtordisp{4294967292,0}' (long,long,void *,long,long *,long *)

- ea: `0x180012a30`
- end: `0x180012a3c`
- name: `?Read@CEditStream@@$4PPPPPPPM@A@EAAJJJPEAXJPEAJ1@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012a44`

## pseudocode

```c
__int64 __fastcall CEditStream::Read(__int64 a1, int a2, int a3, char *a4, unsigned int a5, int *a6, int *a7)
{
  return CEditStream::Read((CEditStream *)(a1 - *(int *)(a1 - 4)), a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180012a30  movsxd  rax, dword ptr [rcx-4]
0x180012a34  sub     rcx, rax; this
0x180012a37  jmp     ?Read@CEditStream@@UEAAJJJPEAXJPEAJ1@Z; CEditStream::Read(long,long,void *,long,long *,long *)
```
