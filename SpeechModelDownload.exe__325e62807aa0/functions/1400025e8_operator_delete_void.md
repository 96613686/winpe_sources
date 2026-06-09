# operator delete(void *)

- ea: `0x1400025e8`
- end: `0x1400025ed`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400028d8`
- `0x1400028f0`

## callees

- `0x140003094`

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
0x1400025e8  jmp     free
```
