# operator delete(void *)

- ea: `0x140001a68`
- end: `0x140001a6e`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001610`
- `0x140001650`
- `0x140001b90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140001a68`

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
0x140001a68  jmp     cs:__imp_??3@YAXPEAX@Z
```
