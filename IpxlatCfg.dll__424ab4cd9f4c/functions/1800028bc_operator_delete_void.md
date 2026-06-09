# operator delete(void *)

- ea: `0x1800028bc`
- end: `0x1800028c1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002110`
- `0x180002120`

## callees

- `0x180002a04`

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
0x1800028bc  jmp     free
```
