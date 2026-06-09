# operator delete(void *)

- ea: `0x1800092fc`
- end: `0x180009301`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008e50`
- `0x180008e60`

## callees

- `0x180009404`

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
0x1800092fc  jmp     free
```
