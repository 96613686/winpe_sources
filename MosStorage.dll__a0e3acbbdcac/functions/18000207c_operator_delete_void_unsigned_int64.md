# operator delete(void *,unsigned __int64)

- ea: `0x18000207c`
- end: `0x180002081`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000694c`
- `0x180006c44`
- `0x180006cd0`
- `0x180006eac`
- `0x18000aa8c`
- `0x18000ac28`
- `0x18000adb8`
- `0x18000ae68`
- `0x18000b5a4`
- `0x18000c860`
- `0x18000c9a0`
- `0x18000cea0`
- `0x18000d4e4`

## callees

- `0x180001c64`

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
0x18000207c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
