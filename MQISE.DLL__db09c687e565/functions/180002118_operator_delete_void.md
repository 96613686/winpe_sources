# operator delete(void *)

- ea: `0x180002118`
- end: `0x180002128`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001a00`
- `0x18000fe68`

## import_xrefs

- `msvcrt!free` at `0x18000211c`
- `msvcrt!free` at `0x18000211c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall operator delete(void *a1)
{
  free(a1);
}

```

## disassembly

```asm
0x180002118  sub     rsp, 28h
0x18000211c  call    cs:__imp_free
0x180002122  nop
0x180002123  add     rsp, 28h
0x180002127  retn
```
