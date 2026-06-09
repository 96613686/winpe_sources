# operator delete(void *)

- ea: `0x18000a111`
- end: `0x18000a117`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000a150`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a111`

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
0x18000a111  jmp     cs:__imp_??3@YAXPEAX@Z
```
