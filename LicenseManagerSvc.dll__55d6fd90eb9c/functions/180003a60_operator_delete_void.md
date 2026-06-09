# operator delete(void *)

- ea: `0x180003a60`
- end: `0x180003a65`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002ed8`
- `0x180003a6c`
- `0x180003a80`
- `0x180003fd0`

## callees

- `0x180004154`

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
0x180003a60  jmp     free
```
