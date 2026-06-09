# operator delete(void *)

- ea: `0x180001ecc`
- end: `0x180001ed1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001e90`
- `0x1800024c0`
- `0x180002580`

## callees

- `0x180002684`

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
0x180001ecc  jmp     free
```
