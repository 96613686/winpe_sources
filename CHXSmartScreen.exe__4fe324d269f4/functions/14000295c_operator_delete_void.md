# operator delete(void *)

- ea: `0x14000295c`
- end: `0x140002962`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `8`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001420`
- `0x1400014a0`
- `0x140001670`
- `0x1400016b0`
- `0x1400019e0`
- `0x140002980`
- `0x140003448`
- `0x140034b90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000295c`

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
0x14000295c  jmp     cs:__imp_??3@YAXPEAX@Z
```
