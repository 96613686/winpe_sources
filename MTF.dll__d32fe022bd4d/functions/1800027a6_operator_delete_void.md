# operator delete(void *)

- ea: `0x1800027a6`
- end: `0x1800027ac`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002150`
- `0x180002190`
- `0x1800028e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800027a6`

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
0x1800027a6  jmp     cs:__imp_??3@YAXPEAX@Z
```
