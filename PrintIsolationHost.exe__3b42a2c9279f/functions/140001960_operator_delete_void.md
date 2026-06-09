# operator delete(void *)

- ea: `0x140001960`
- end: `0x140001965`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001f64`
- `0x1400072e0`

## callees

- `0x140002654`

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
0x140001960  jmp     free
```
