# operator delete(void *)

- ea: `0x180001fe4`
- end: `0x180001fe9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002024`
- `0x180002450`

## callees

- `0x180002a44`

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
0x180001fe4  jmp     free
```
