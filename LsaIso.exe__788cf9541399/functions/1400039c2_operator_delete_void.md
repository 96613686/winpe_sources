# operator delete(void *)

- ea: `0x1400039c2`
- end: `0x1400039c8`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140003860`
- `0x1400038a0`
- `0x140003a10`
- `0x140003a70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400039c2`

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
0x1400039c2  jmp     cs:__imp_??3@YAXPEAX@Z
```
