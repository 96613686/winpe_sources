# operator delete(void *)

- ea: `0x1800038d4`
- end: `0x1800038d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003914`
- `0x180003d40`

## callees

- `0x180004664`

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
0x1800038d4  jmp     free
```
