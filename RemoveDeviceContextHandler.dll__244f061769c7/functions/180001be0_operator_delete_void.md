# operator delete(void *)

- ea: `0x180001be0`
- end: `0x180001be5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001bec`
- `0x180005adc`
- `0x180005d1c`
- `0x180005f24`
- `0x180006250`
- `0x1800062b0`
- `0x180006310`
- `0x180006370`
- `0x1800063d0`
- `0x180006410`
- `0x180007800`
- `0x180007a10`
- `0x18000a210`
- `0x18000b5dc`
- `0x18000c0b0`
- `0x18000c160`

## callees

- `0x1800021f8`

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
0x180001be0  jmp     free_0
```
