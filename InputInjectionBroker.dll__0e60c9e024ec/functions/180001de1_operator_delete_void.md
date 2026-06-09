# operator delete(void *)

- ea: `0x180001de1`
- end: `0x180001de7`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800016f0`
- `0x180001730`
- `0x180001e30`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001de1`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  __imp_??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180001de1  jmp     cs:__imp_??3@YAXPEAX@Z
```
