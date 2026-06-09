# operator delete(void *)

- ea: `0x180001790`
- end: `0x180001795`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800031a8`
- `0x180003800`
- `0x180003830`
- `0x180008d70`
- `0x180008fe0`
- `0x180009bf0`
- `0x18000a740`
- `0x18000a7b0`

## callees

- `0x180001f8a`

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
0x180001790  jmp     free_0
```
