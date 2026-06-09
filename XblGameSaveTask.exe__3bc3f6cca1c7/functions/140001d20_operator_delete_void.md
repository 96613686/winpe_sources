# operator delete(void *)

- ea: `0x140001d20`
- end: `0x140001d25`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001714`
- `0x140001720`

## callees

- `0x140001efa`

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
0x140001d20  jmp     free
```
