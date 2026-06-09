# operator delete(void *)

- ea: `0x140002918`
- end: `0x14000291d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002954`
- `0x140002cf0`

## callees

- `0x140003454`

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
0x140002918  jmp     free
```
