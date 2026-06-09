# operator delete(void *)

- ea: `0x140001200`
- end: `0x140001205`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000124c`
- `0x140001970`
- `0x1400021d8`
- `0x1400036d0`
- `0x140004a10`

## callees

- `0x140001632`

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
0x140001200  jmp     free_0
```
