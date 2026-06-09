# operator delete(void *)

- ea: `0x140001900`
- end: `0x140001905`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001614`
- `0x140001620`

## callees

- `0x140002286`

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
0x140001900  jmp     free_0
```
