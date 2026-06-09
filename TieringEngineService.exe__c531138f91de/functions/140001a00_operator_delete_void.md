# operator delete(void *)

- ea: `0x140001a00`
- end: `0x140001a05`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001a0c`
- `0x140001f10`
- `0x140002bd0`
- `0x140002c10`
- `0x140002c50`
- `0x140002c90`
- `0x140002cd0`
- `0x140003380`
- `0x140003dc0`
- `0x140003e38`
- `0x140004614`
- `0x1400046d4`
- `0x140005284`
- `0x1400055ec`
- `0x1400057f8`
- `0x14000761c`
- `0x140014e28`
- `0x1400166f4`
- `0x140016a44`
- `0x14002d3c4`
- `0x140031e04`
- `0x14003ddd4`
- `0x14003ffa1`
- `0x14004005a`

## callees

- `0x14000201c`

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
0x140001a00  jmp     free_0
```
