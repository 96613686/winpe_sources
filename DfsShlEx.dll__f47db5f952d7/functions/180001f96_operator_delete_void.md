# operator delete(void *)

- ea: `0x180001f96`
- end: `0x180001f9c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800012a0`
- `0x1800012d0`
- `0x180001310`
- `0x180001348`
- `0x180001448`
- `0x180002430`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001f96`

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
0x180001f96  jmp     cs:__imp_??3@YAXPEAX@Z
```
