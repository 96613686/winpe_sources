# operator delete(void *)

- ea: `0x18000a1a8`
- end: `0x18000a1ad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a1c0`
- `0x18000a210`
- `0x18000a3c0`

## callees

- `0x18000a16a`

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
0x18000a1a8  jmp     free
```
