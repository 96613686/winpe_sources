# operator delete(void *)

- ea: `0x140001ba0`
- end: `0x140001ba6`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1400016e0`
- `0x140001720`
- `0x140001bf0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140001ba0`

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
0x140001ba0  jmp     cs:__imp_??3@YAXPEAX@Z
```
