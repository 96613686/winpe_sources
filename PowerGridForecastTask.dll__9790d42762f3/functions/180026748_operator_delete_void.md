# operator delete[](void *)

- ea: `0x180026748`
- end: `0x18002674e`
- name: `??_V@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `13`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180003330`
- `0x1800033a0`
- `0x18000670c`
- `0x18000b7c0`
- `0x18000b830`
- `0x18000b9a0`
- `0x18000ba00`
- `0x18000ba60`
- `0x18000bac0`
- `0x180015860`
- `0x1800158fc`
- `0x18001d6b0`
- `0x18001d770`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180026748`

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
0x180026748  jmp     cs:__imp_??_V@YAXPEAX@Z
```
