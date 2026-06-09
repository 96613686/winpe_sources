# operator delete(void *)

- ea: `0x1800025f6`
- end: `0x1800025fc`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001fc0`
- `0x180002000`
- `0x180002620`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800025f6`

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
0x1800025f6  jmp     cs:__imp_??3@YAXPEAX@Z
```
