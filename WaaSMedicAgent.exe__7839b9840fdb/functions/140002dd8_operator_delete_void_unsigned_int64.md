# operator delete(void *,unsigned __int64)

- ea: `0x140002dd8`
- end: `0x140002ddd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004670`
- `0x140004870`
- `0x1400048b0`
- `0x140007a38`
- `0x140007b30`
- `0x140007ba4`
- `0x140007c0c`
- `0x140007d60`
- `0x140007dc0`
- `0x140007e1c`
- `0x140009c0c`
- `0x14000a8f0`
- `0x14000bbf0`
- `0x14000c0f0`
- `0x14000c130`
- `0x14000e9c4`
- `0x14000f34c`
- `0x1400108c8`

## callees

- `0x140002a18`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x140002dd8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
