# operator delete(void *)

- ea: `0x180026609`
- end: `0x18002660f`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `82`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002250`
- `0x180002290`
- `0x1800024e0`
- `0x180002a24`
- `0x180003300`
- `0x180003330`
- `0x1800033a0`
- `0x1800034a4`
- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x180005b54`
- `0x18000673c`
- `0x1800074b0`
- `0x180007f20`
- `0x180008c34`
- `0x180008e00`
- `0x18000b6a4`
- `0x18000b7c0`
- `0x18000b830`
- `0x18000b8a0`
- `0x18000b8f0`
- `0x18000b940`
- `0x18000b9a0`
- `0x18000ba00`
- `0x18000ba60`
- `0x18000bac0`
- `0x18000bb20`
- `0x18000bbe0`
- `0x18000bd00`
- `0x18000c1a0`
- `0x18000c720`
- `0x18000c83c`
- `0x18000d948`
- `0x18000e050`
- `0x18000e758`
- `0x18000eee8`
- `0x18000fa28`
- `0x18000fe64`
- `0x18001046c`
- `0x18001108c`
- `0x1800124d0`
- `0x180012884`
- `0x180014638`
- `0x180014eb4`
- `0x180015898`
- `0x180016290`
- `0x1800163a0`
- `0x180016500`
- `0x180016610`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026609`

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
0x180026609  jmp     cs:__imp_??3@YAXPEAX@Z
```
