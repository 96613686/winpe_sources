# operator delete(void *)

- ea: `0x18000437c`
- end: `0x180004381`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b20`
- `0x180002090`
- `0x1800027a0`
- `0x1800030d0`
- `0x180003110`
- `0x1800040e0`
- `0x180004d44`
- `0x180005090`
- `0x180005120`
- `0x180005150`
- `0x180005190`

## callees

- `0x1800048b2`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x18000437c  jmp     free_0
```
