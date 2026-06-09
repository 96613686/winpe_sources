# operator delete(void *)

- ea: `0x180008f22`
- end: `0x180008f28`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800087c0`
- `0x180008f80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008f22`

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
0x180008f22  jmp     cs:__imp_??3@YAXPEAX@Z
```
