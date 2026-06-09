# operator delete(void *)

- ea: `0x18002a43c`
- end: `0x18002a441`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ac14`
- `0x18000acf4`
- `0x18001314c`
- `0x180013a94`
- `0x180014d70`
- `0x18001c6bc`
- `0x18001f5f4`
- `0x180028be4`
- `0x18002a400`
- `0x18002a410`
- `0x18002fee0`
- `0x180030000`
- `0x180031f30`

## callees

- `0x18002aaa0`

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
0x18002a43c  jmp     free
```
