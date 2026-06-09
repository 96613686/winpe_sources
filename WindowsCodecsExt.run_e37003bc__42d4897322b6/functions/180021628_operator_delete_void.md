# operator delete(void *)

- ea: `0x180021628`
- end: `0x18002162d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007bb0`
- `0x180013670`
- `0x18001883c`
- `0x180021a54`

## callees

- `0x180022324`

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
0x180021628  jmp     free
```
