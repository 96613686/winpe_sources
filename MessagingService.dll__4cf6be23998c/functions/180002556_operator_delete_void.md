# operator delete(void *)

- ea: `0x180002556`
- end: `0x18000255c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `7`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001860`
- `0x180001890`
- `0x1800018d0`
- `0x180001908`
- `0x180001a08`
- `0x18000266c`
- `0x180002720`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002556`

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
0x180002556  jmp     cs:__imp_??3@YAXPEAX@Z
```
