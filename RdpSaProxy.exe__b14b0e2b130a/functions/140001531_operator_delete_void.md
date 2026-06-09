# operator delete(void *)

- ea: `0x140001531`
- end: `0x140001537`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001c70`
- `0x140001ca0`
- `0x140001ce0`
- `0x140001d18`
- `0x140001e18`
- `0x140002530`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140001531`

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
0x140001531  jmp     cs:__imp_??3@YAXPEAX@Z
```
