# operator delete(void *)

- ea: `0x180002f78`
- end: `0x180002f7d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002f84`
- `0x180002f90`
- `0x1800053d0`

## callees

- `0x180003614`

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
0x180002f78  jmp     free
```
