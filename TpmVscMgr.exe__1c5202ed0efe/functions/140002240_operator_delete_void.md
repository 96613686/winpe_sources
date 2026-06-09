# operator delete(void *)

- ea: `0x140002240`
- end: `0x140002245`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001934`
- `0x140001940`

## callees

- `0x14000240e`

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
0x140002240  jmp     free
```
