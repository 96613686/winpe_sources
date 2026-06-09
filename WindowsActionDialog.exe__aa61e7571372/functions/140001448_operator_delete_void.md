# operator delete(void *)

- ea: `0x140001448`
- end: `0x14000144d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000175c`
- `0x140001770`

## callees

- `0x140001f14`

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
0x140001448  jmp     free
```
