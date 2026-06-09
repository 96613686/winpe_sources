# operator delete(void *)

- ea: `0x1800021dc`
- end: `0x1800021e1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001d30`
- `0x180001d40`

## callees

- `0x1800022d2`

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
0x1800021dc  jmp     free
```
