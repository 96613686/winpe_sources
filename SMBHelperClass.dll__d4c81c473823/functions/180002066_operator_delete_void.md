# operator delete(void *)

- ea: `0x180002066`
- end: `0x18000206c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001370`
- `0x1800013a0`
- `0x1800013e0`
- `0x180001418`
- `0x180001518`
- `0x1800020b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002066`

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
0x180002066  jmp     cs:__imp_??3@YAXPEAX@Z
```
