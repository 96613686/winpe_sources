# operator delete[](void *)

- ea: `0x1800019e6`
- end: `0x1800019ec`
- name: `??_V@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800019e6`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *a1)
{
  __imp_??_V@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x1800019e6  jmp     cs:__imp_??_V@YAXPEAX@Z
```
