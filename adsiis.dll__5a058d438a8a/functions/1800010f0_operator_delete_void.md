# operator delete(void *)

- ea: `0x1800010f0`
- end: `0x1800010f5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `41`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a28`
- `0x180001a98`
- `0x180001e50`
- `0x180001e78`
- `0x180002620`
- `0x1800026b0`
- `0x1800026e8`
- `0x180002a90`
- `0x180002ab8`
- `0x180003aac`
- `0x180003b80`
- `0x1800042c0`
- `0x1800042e8`
- `0x1800048e8`
- `0x180008144`
- `0x180009480`
- `0x1800094a8`
- `0x1800094d0`
- `0x18000c11c`
- `0x18000cd44`
- `0x18000cdf0`
- `0x18000d3b0`
- `0x18000d524`
- `0x18000d600`
- `0x18000dc44`
- `0x18000e1d0`
- `0x18000f784`
- `0x18000fee8`
- `0x1800147d8`
- `0x1800169d4`
- `0x1800192e4`
- `0x18001941c`
- `0x180019b58`
- `0x180019bec`
- `0x180019cb4`
- `0x18001a0a0`
- `0x18001a578`
- `0x18001b278`
- `0x18001b5ec`
- `0x18001c0d4`
- `0x18001c2dc`

## callees

- `0x1800017ec`

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
0x1800010f0  jmp     free_0
```
