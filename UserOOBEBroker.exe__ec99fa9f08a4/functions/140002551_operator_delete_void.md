# operator delete(void *)

- ea: `0x140002551`
- end: `0x140002557`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001f70`
- `0x140001fb0`
- `0x1400025a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140002551`

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
0x140002551  jmp     cs:__imp_??3@YAXPEAX@Z
```
