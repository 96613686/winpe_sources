# operator delete(void *)

- ea: `0x180001ead`
- end: `0x180001eb3`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001190`
- `0x1800011c0`
- `0x180001200`
- `0x180001238`
- `0x180001338`
- `0x180002210`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001ead`

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
0x180001ead  jmp     cs:__imp_??3@YAXPEAX@Z
```
