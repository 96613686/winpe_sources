# operator delete(void *)

- ea: `0x1800021e0`
- end: `0x1800021e5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001bf8`
- `0x1800024b0`
- `0x180014cb0`
- `0x1800150c0`
- `0x180036b70`
- `0x180036ba0`

## callees

- `0x1800025fc`

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
0x1800021e0  jmp     free
```
