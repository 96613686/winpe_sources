# operator delete(void *)

- ea: `0x180001e3c`
- end: `0x180001e41`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001960`
- `0x180001970`

## callees

- `0x180001f32`

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
0x180001e3c  jmp     free
```
