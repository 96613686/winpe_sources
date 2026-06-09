# operator delete(void *)

- ea: `0x1800024ae`
- end: `0x1800024b4`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001c80`
- `0x180001cb0`
- `0x180001cf0`
- `0x180001d28`
- `0x180001e28`
- `0x1800024c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800024ae`

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
0x1800024ae  jmp     cs:__imp_??3@YAXPEAX@Z
```
