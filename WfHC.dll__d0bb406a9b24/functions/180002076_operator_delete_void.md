# operator delete(void *)

- ea: `0x180002076`
- end: `0x18000207c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001380`
- `0x1800013b0`
- `0x1800013f0`
- `0x180001428`
- `0x180001528`
- `0x1800024d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002076`

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
0x180002076  jmp     cs:__imp_??3@YAXPEAX@Z
```
