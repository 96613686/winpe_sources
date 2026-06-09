# operator delete(void *)

- ea: `0x180001aa4`
- end: `0x180001aa9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002fd4`
- `0x1800032d8`
- `0x180003570`
- `0x1800035b0`
- `0x1800035f0`

## callees

- `0x180001f76`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001aa4  jmp     free_0
```
