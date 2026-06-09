# operator delete(void *)

- ea: `0x1400011d4`
- end: `0x1400011d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001c80`
- `0x140004730`
- `0x140006a88`
- `0x140006e24`
- `0x1400076e0`
- `0x140008090`
- `0x140008710`
- `0x14000aaa4`

## callees

- `0x1400014e6`

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
