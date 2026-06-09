# operator delete(void *)

- ea: `0x1800131b1`
- end: `0x1800131b7`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180011b20`
- `0x180011fb0`
- `0x180013200`
- `0x180024cf0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800131b1`

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
0x1800131b1  jmp     cs:__imp_??3@YAXPEAX@Z
```
