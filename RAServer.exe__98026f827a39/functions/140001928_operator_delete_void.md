# operator delete(void *)

- ea: `0x140001928`
- end: `0x14000192e`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001400`
- `0x140001440`
- `0x140001ea0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140001928`

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
0x140001928  jmp     cs:__imp_??3@YAXPEAX@Z
```
