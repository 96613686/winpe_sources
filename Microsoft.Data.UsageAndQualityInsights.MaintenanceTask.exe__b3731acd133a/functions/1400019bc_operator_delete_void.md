# operator delete(void *)

- ea: `0x1400019bc`
- end: `0x1400019c1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001984`
- `0x140001990`

## callees

- `0x1400021d4`

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
0x1400019bc  jmp     free
```
