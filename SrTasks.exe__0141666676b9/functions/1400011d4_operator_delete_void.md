# operator delete(void *)

- ea: `0x1400011d4`
- end: `0x1400011d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140008c30`
- `0x14000d688`

## callees

- `0x140001526`

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
0x1400011d4  jmp     free_0
```
