# operator delete(void *)

- ea: `0x140001b90`
- end: `0x140001b95`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400015f4`
- `0x140001600`

## callees

- `0x140001fae`

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
0x140001b90  jmp     free_0
```
