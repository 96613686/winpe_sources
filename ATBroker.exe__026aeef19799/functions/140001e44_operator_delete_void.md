# operator delete(void *)

- ea: `0x140001e44`
- end: `0x140001e49`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002a20`
- `0x140004040`
- `0x140004070`
- `0x14000b920`
- `0x14000b950`
- `0x14000bdf4`
- `0x14000c27c`
- `0x14000c8b4`
- `0x140015ff6`

## callees

- `0x14000241c`

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
0x140001e44  jmp     free_0
```
