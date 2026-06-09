# operator delete(void *)

- ea: `0x180001c90`
- end: `0x180001c95`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001644`
- `0x180001a70`
- `0x1800095d0`
- `0x1800099b0`
- `0x18000a65c`
- `0x18000ab90`
- `0x18000b160`
- `0x18000b190`

## callees

- `0x180002094`

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
0x180001c90  jmp     free
```
