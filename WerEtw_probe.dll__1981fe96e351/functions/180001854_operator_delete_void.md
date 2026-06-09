# operator delete(void *)

- ea: `0x180001854`
- end: `0x180001859`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001894`
- `0x180002280`
- `0x180026530`
- `0x180026560`

## callees

- `0x1800023d8`

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
0x180001854  jmp     free
```
