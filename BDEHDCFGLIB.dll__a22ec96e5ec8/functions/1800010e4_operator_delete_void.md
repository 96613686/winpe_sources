# operator delete(void *)

- ea: `0x1800010e4`
- end: `0x1800010e9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f00`
- `0x180001f80`
- `0x180007970`
- `0x180007af0`
- `0x180009c78`
- `0x180009d60`
- `0x180009db0`
- `0x180009e00`
- `0x180009e70`
- `0x180009ee0`
- `0x180009f40`
- `0x180009fa0`
- `0x180009fe0`
- `0x18000b2c0`
- `0x18000ca9c`
- `0x18000cb40`
- `0x18000ce00`
- `0x18000cf70`
- `0x18000cfb0`
- `0x18000f030`

## callees

- `0x18000191c`

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
0x1800010e4  jmp     free_0
```
