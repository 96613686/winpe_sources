# operator delete(void *)

- ea: `0x1400033bc`
- end: `0x1400033c1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003224`
- `0x1400033d0`
- `0x140003560`
- `0x140004ab4`
- `0x14000a804`

## callees

- `0x140002f74`

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
0x1400033bc  jmp     free
```
