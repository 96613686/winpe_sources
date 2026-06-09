# operator delete(void *)

- ea: `0x1800033b4`
- end: `0x1800033b9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800033f4`
- `0x180003820`

## callees

- `0x180004134`

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
0x1800033b4  jmp     free
```
