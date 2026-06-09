# operator delete(void *)

- ea: `0x14000aff8`
- end: `0x14000affd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000a624`
- `0x14000a630`
- `0x14000d460`

## callees

- `0x14000a36b`

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
0x14000aff8  jmp     free
```
