# operator delete(void *)

- ea: `0x180005064`
- end: `0x180005069`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800017a8`
- `0x180005070`
- `0x180005080`

## callees

- `0x1800056b0`

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
0x180005064  jmp     free
```
