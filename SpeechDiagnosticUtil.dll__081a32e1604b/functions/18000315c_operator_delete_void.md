# operator delete(void *)

- ea: `0x18000315c`
- end: `0x180003161`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002ce0`
- `0x180003470`
- `0x180003530`

## callees

- `0x180003254`

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
0x18000315c  jmp     free
```
