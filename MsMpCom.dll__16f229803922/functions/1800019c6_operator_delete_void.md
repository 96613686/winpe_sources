# operator delete(void *)

- ea: `0x1800019c6`
- end: `0x1800019cc`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800013a0`
- `0x1800013e0`
- `0x180001ba0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800019c6`

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
0x1800019c6  jmp     cs:__imp_??3@YAXPEAX@Z
```
