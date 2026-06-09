# operator delete(void *)

- ea: `0x180001098`
- end: `0x18000109f`
- name: `??3@YAXPEAX@Z`
- size: `7`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001330`
- `0x180001374`
- `0x1800013d0`
- `0x180001444`
- `0x180001638`
- `0x180001ed0`
- `0x180003174`
- `0x1800031d0`
- `0x180003210`
- `0x180003330`
- `0x1800035a4`
- `0x18000372c`
- `0x180003d30`

## import_xrefs

- `msvcrt!free` at `0x180001098`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001098  jmp     cs:__imp_free
```
