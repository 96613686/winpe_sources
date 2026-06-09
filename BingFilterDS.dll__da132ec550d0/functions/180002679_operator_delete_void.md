# operator delete(void *)

- ea: `0x180002679`
- end: `0x18000267f`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001f30`
- `0x180001f70`
- `0x1800026e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002679`

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
0x180002679  jmp     cs:__imp_??3@YAXPEAX@Z
```
