# operator delete(void *)

- ea: `0x180001bad`
- end: `0x180001bb3`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001bf0`
- `0x180020c90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001bad`

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
0x180001bad  jmp     cs:__imp_??3@YAXPEAX@Z
```
