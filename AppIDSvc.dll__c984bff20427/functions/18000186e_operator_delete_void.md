# operator delete(void *)

- ea: `0x18000186e`
- end: `0x180001874`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800012d0`
- `0x180001880`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000186e`

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
0x18000186e  jmp     cs:__imp_??3@YAXPEAX@Z
```
